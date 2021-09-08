NOTE: Please keep in mind we regularly update our testnet and potentially wipe out existing history

## Download JAR

Currently running **v0.8.9** ([download](https://github.com/alephium/alephium/releases/download/v0.8.9/alephium-0.8.9.jar))

Block explorer: [https://testnet.alephium.org](https://testnet.alephium.org)

## Configure your node

Before starting the node, you should set the following content in the file `~/.alephium/user.conf`:

    alephium.network.network-type = "testnet"
    alephium.discovery.bootstrap = ["3.68.2.201:9973", "34.236.121.90:9973", "54.252.31.241:9973"]
    alephium.network.external-address = "x.x.x.x:9973" // put your static IP address here; otherwise comment this line out
    // alephium.mining.miner-addresses = ["T151XWPo8AzfK14TWux2JMV5NKkStLhkXqqcYZNy8hoM6J","T19Fb9yrYbKLFke12cjNiQYRo9SErS3wyCz68abaS4Kumy","T1C8b4fUbojXEZMnvDZZdcCts3FXkHyhFTLb22s88EnHxs","T1ZL4ZX8FL55VRcqsJaR9QwPwy5AUtMVxKvgUzwRprr8Q"] // put your miner addresses here if necessary

NOTE:
* If you are upgrading from a previous release, please ensure `~/.alephium` is clean of any `db-*` folders

## Start your node
You are now ready to start your node using the JAR you downloaded earlier.

    java -jar -Xmx500m alephium-0.8.9.jar

If running on Unix system, please ensure the system is providing enough entropy or setup an agent like `haveged`.

NOTE: The log files will be stored in `~/.alephium/logs`

## Getting Started

### Tools

You can use Swagger (or any other openapi clients). We recommand Swagger as it provide the most straightforward UX.

### Swagger

You can directly open Swagger UI through `http://127.0.0.1:12973/docs`.

Alternatively, you can also import the API using "File - Import file",
when prompted select the file `openapi.json` which you can [download](https://github.com/alephium/alephium/raw/master/api/src/main/resources/openapi.json) from our repository.

### Mining

You can follow our guide for mining to get some coins first: [https://github.com/alephium/alephium/wiki/Miner-Guide](https://github.com/alephium/alephium/wiki/Miner-Guide)

## Wallet

Our full node has a builtin wallet, you can find the guide on how to use it here: [https://github.com/alephium/alephium/wiki/Wallet-Guide](https://github.com/alephium/alephium/wiki/Miner-Guide)
