NOTE: Please keep in mind we regularly update our testnet and potentially wipe out existing history

## Download JAR

Currently running **v0.11.4** ([download](https://github.com/alephium/alephium/releases/download/v0.11.4/alephium-0.11.4.jar))

Block explorer: [https://testnet.alephium.org](https://testnet.alephium.org)

## Configure your node

Before starting the node, you should set the following content in the file `~/.alephium/user.conf`:

    alephium.network.network-id = 1
    alephium.discovery.bootstrap = ["18.156.2.99:9973", "18.156.163.31:9973", "3.64.55.68:9973"]
    alephium.network.external-address = "x.x.x.x:9973" // put your static IP address here; otherwise comment this line out
    // alephium.mining.miner-addresses = ["17dReod9M5iLsf87ebJGLa4ybRZcFog1ewV6y2zUNHWu5","14FGvG61tqzXXYi6UKtzjozMjxCArF1beoU4ogUqM2pSG","15qNxou4d5AnPkTgS93xezWpSyZgqegNjjf41QoMqi5Bf","1BDwKf9SPzrzQ6wBeWfUNB9yi615MEM9zJeHfkvPnmVnW"] // put your miner addresses here if necessary

NOTE:
* If you are upgrading from a previous release, please ensure `~/.alephium` is clean of any `db-*` folders

## Start your node
You are now ready to start your node using the JAR you downloaded earlier.

    java -jar -Xmx500m alephium-0.11.4.jar

If running on Unix system, please ensure the system is providing enough entropy or setup an agent like `haveged`.

The config files will be under `~/.alephium/`, and the log files will be stored in `~/.alephium/logs`.
There are comments of many of the config parameters in those config files.

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

Our full node has a builtin wallet, you can find the guide on how to use it here: [https://github.com/alephium/alephium/wiki/Wallet-Guide](https://github.com/alephium/alephium/wiki/Wallet-Guide)
