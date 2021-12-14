# Mining Pool Test

> This is for testing for now

### Setup Mining Proxy

1. Clone project [https://github.com/alephium/mining-proxy](https://github.com/alephium/mining-proxy)
2. Open `config.json` and set `serverHost` as `52.18.87.57`
3. Open `config.json` and set `addresses` as your 4 mining addresses
4. Start the proxy with `npm install && npm start`


### Start mining

Launch your miner with `gpu-miner -p 30032`. You should see new blocks mined. Please note that blocks are shares, We will rename it in the next release.
