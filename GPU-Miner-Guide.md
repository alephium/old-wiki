You must first follow the steps in the [[Testnet Guide]], in order to download, configure, start your node and use Swagger (or any other OpenAPI clients).

### Create a new miner wallet

First, you must create a dedicated wallet for mining (as opposed to a *traditional wallet*, a *miner wallet* have multiple addresses which are used to collect mining rewards for each group).

You can create a miner wallet (please note the definition of the field `isMiner`) by doing a POST with the following data on `/wallets`.

    {
        "password": "123456",
        "walletName": "bar",
        "isMiner": true
    }

The server must answer successfully giving you our new wallet mnemonic.

    {
        "walletName": "bar",
        "mnemonic": "laptop tattoo torch range exclude fuel bike menu just churn then busy century select cactus across other merge vivid alarm asset genius mountain transfer"
    }

Fetch your new wallet addresses by GET `/wallets/bar/addresses`.

    {
      "activeAddress": "18xRk6dY3ozPpSmdKqA7xYgncB6mR5QtgV512N6FU2mPr",
      "addresses": [
        "1HA4d4YpHZwbCvCMwFiXATzSj2M5BJSL8wt3XSR7PaXGk",
        "18cRGxiEMvhCBMZTA9FhFX1LXkRYaVM4BvBE971uUQ6zt",
        "18zntGYAHjbo6EPoe3aWQdfVF4twxQwPLn3bGq5tzG4Mq",
        "18xRk6dY3ozPpSmdKqA7xYgncB6mR5QtgV512N6FU2mPr"
      ]
    }

Our miner wallet has four addresses as the testnet is running with 4 groups.

#### Assign your miner wallet to your node

Now that you have created the wallet that will receive your mining, you must assign it to your node so you can earn rewards when it starts mining.

##### 1. Using an endpoint

The miner addresses could also be defined dynamically by doing a PUT on the `/miners/addresses` endpoint, refer to the openapi specification for more detail.

##### 2. Using configuration

Alternatively, this can be done by adding the following content in the file ~/.alephium/user.conf:

    alephium.mining.miner-addresses = [
      "1HA4d4YpHZwbCvCMwFiXATzSj2M5BJSL8wt3XSR7PaXGk",
      "18cRGxiEMvhCBMZTA9FhFX1LXkRYaVM4BvBE971uUQ6zt",
      "18zntGYAHjbo6EPoe3aWQdfVF4twxQwPLn3bGq5tzG4Mq",
      "18xRk6dY3ozPpSmdKqA7xYgncB6mR5QtgV512N6FU2mPr"
    ]

Please be sure to add them in the same order they were returned by the endpoint, as they are sorted according to their group.
You will need to restart your node for the changes to be taken into account.

### Start mining

The GPU miner is only CUDA compatible for now. Please follow the instructions on [https://github.com/alephium/gpu-miner](https://github.com/alephium/gpu-miner) to build and run the miner.

Alternatively, you could run the gpu-miner with docker by following the documents here [https://github.com/alephium/alephium/tree/master/docker#gpu-miner-optional](https://github.com/alephium/alephium/tree/master/docker#gpu-miner-optional)

If you have any questions, feel free to reach out to the developers on [Discord](https://discord.gg/4BEUkc9zpA).
