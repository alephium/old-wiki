# Pool Mining Guide

Here is a list of mining pools. Please visit their websites for more information.

* Devgent pool: [https://pool.devgent.net](https://pool.devgent.net)
* Metapool: [https://metapool.tech](https://metapool.tech)
* WoolyPooly: [https://woolypooly.com/en/coin/alph](https://woolypooly.com/en/coin/alph)
* HeroMiners: [https://alephium.herominers.com/](https://alephium.herominers.com/)

If you want to host your own mining pool, please checkout the repo here: [https://github.com/alephium/mining-pool/](https://github.com/alephium/mining-pool/)

### Example node configuration for mining pool:

> This section is for pool operators, not for miners.

```
// more connections for better block propagation
alephium.network.external-address = "<public IP for discovery>:9973"
alephium.network.max-outbound-connections-per-group = 48
alephium.network.max-inbound-connections-per-group  = 256

alephium.mining.miner-addresses = [4 miner addresses]

// comment out the following 2 lines if you don't access rest api from external network
alephium.api.network-interface = "0.0.0.0"
alephium.api.api-key = "<api key>"
```