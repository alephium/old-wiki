## Download JAR

Currently running **v1.0.0** ([download](https://github.com/alephium/alephium/releases/download/v1.0.0/alephium-1.0.0.jar))

Block explorer: [https://explorer.alephium.org](https://explorer.alephium.org)

## Start your node
You could start your node using the JAR you downloaded earlier.

    java -jar -Xmx500m alephium-1.0.0.jar

The config files and database will be under `~/.alephium/mainnet`, the log files will be stored in `~/.alephium/logs`.
There are comments of many of the config parameters in those config files.

## Configure your node (Optional)

You could set the following content in the file `~/.alephium/user.conf`:

    alephium.network.external-address = "x.x.x.x:9973" // put your static IP address here; otherwise comment this line out
    // alephium.mining.miner-addresses = ["17dReod9M5iLsf87ebJGLa4ybRZcFog1ewV6y2zUNHWu5","14FGvG61tqzXXYi6UKtzjozMjxCArF1beoU4ogUqM2pSG","15qNxou4d5AnPkTgS93xezWpSyZgqegNjjf41QoMqi5Bf","1BDwKf9SPzrzQ6wBeWfUNB9yi615MEM9zJeHfkvPnmVnW"] // put your miner addresses here if necessary

Please restart your node to make these new configs take effect.

## Getting Started

### Swagger

We use OpenApi to interact with the full node. You can directly open Swagger UI through `http://127.0.0.1:12973/docs`.

Alternatively, you can use any OpenAPI client to
import the `openapi.json` file from our repository [download](https://github.com/alephium/alephium/raw/master/api/src/main/resources/openapi.json).

### Mining

You can follow our guide for mining to get some coins first: [https://github.com/alephium/alephium/wiki/GPU-Miner-Guide](https://github.com/alephium/alephium/wiki/GPU-Miner-Guide)

## Wallet

You could download the desktop wallet from here: [https://github.com/alephium/alephium-wallet/releases/tag/v1.0.0](https://github.com/alephium/alephium-wallet/releases/tag/v1.0.0)

Alternatively, our full node has a builtin wallet with advanced features, you can find the guide on how to use it here: [https://github.com/alephium/alephium/wiki/Wallet-Guide](https://github.com/alephium/alephium/wiki/Wallet-Guide)
