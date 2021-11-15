# Mining companion for your Alephium full node

Mining is the activity of securing the blockchain providing compute power, while getting
mining block rewards in counterpart. Every block you mine has a reward attached to it,
and this reward is sent to the mining wallet that has successfully mined the block.

On the Alephium blockchain, a mining wallet has multiple addresses referring to it,
precisely one address per chain in the blockchain.
Alephium mainnet has currently 4 groups, so a mining wallet for the mainnet has 4 addresses.

So when you're mining on Alephium blockchain, you'll soon end up having
ALPH spread on all the addresses of your mining wallet.

So if you want to centralize the mining block rewards
to a normal wallet (with a single address), the mining companion will help you automating this task!

## The mining companion

The mining companion is a lightweight, standalone process which, in a nutshell,
will connect to a Alephium full node to transfer the block rewards from all the addresses of your mining wallet
to a normal, single address wallet.
This transfer operation happens at a regular frequency, for instance every 15 minutes.
At the trigger time, if the available (unlocked) amount is bigger than a certain threshold,
say 20 ALPH, this amount is transferred to your normal wallet. So block rewards are grouped
together to limit transaction fee.

## Configuration

So let's get started and run a mining companion.

The best way to run the mining companion is via Docker and [docker-compose](https://docs.docker.com/compose/).
This guide assumes you have docker and docker-compose already installed
on your computer. Please refer to the [official documentation](https://docs.docker.com/compose/install/) to install
these two technologies otherwise.
You might even have your [Alephium full node running in a docker container](TODO LINK), but this step is not mandatory.

In a `docker-compose.yml` file, define the `mining-companion` service as the following:

```yaml
version: "3"
services:
  mining-companion:
    image: touilleio/alephium-mining-companion:v4
    restart: unless-stopped
    security_opt:
      - no-new-privileges:true
    environment:
      - ALEPHIUM_ENDPOINT=http://broker:12973
      - TRANSFER_ADDRESS=YOUR WALLET ADDRESS HERE!!
    labels:
      - org.label-schema.group=alephium
```

In the snippet above, replace `YOUR WALLET ADDRESS HERE!!` by the address of you normal wallet, for instance
`14FGvG61tqzXXYi6UKtzjozMjxCArF1beoU4ogUqM2pAC` and make sure `ALEPHIUM_ENDPOINT` points to
your Alephium full node endpoint. Using `http://localhost:12973` here is always wrong!

This is it, all the other default configuration options are safe to run. All the configuration options
are listed in the [README file of the project source code](https://github.com/touilleio/alephium-mining-companion.

You can then simply start the process, using `docker-compose up -d mining-companion`, and it will
start transferring the block rewards to the address you put in the `TRANSFER_ADDRESS` variable.

> **DISCLAIMER**: If you put a wrong address in `TRANSFER_ADDRESS`, your ALPH rewards cannot be used anymore (or at least not by you)!
>
> So double check this address to avoid any mistake.

## Recommendations

It is recommended to run one mining companion per Alephium full node, so that the
mining wallet password stays local to the full node.
