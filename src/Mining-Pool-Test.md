# Mining Pool Test

> This is for testing for now

You will need to setup mining proxy, then start your miner. Mining proxy is the middleware between the mining pool and your miner.

## Setup Mining Proxy

You could choose to run the pre-built proxy or run it from source code.

### Pre-built Mining Proxy

1. Download the latest version of mining proxy from [Release](https://github.com/alephium/mining-proxy/releases)
2. Create file `config.json` with the same content as this [Template](https://raw.githubusercontent.com/alephium/mining-proxy/master/config.json)
3. Modify `config.json` and set `serverHost` as `52.18.87.57`
4. Modify `config.json` and set `addresses` as your 4 mining addresses
5. Start the proxy in Command Prompt (Windows) or Terminal (Linux)

### Proxy from Source Code

1. Clone project [https://github.com/alephium/mining-proxy](https://github.com/alephium/mining-proxy)
2. Open `config.json` and set `serverHost` as `52.18.87.57`
3. Open `config.json` and set `addresses` as your 4 mining addresses
4. Start the proxy with `npm install && npm start`


## Start mining

Launch your miner with `gpu-miner -p 30032`. You should see new blocks mined. Please note that blocks are shares, We will rename it in the next release.
