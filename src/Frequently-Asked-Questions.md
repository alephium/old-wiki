# Frequently Asked Questions

Here is a compilation of Frequently Asked Questions. For more elaboration on some of the topics check the [Official Medium.](https://medium.com/@alephium) You might be specifically interested in [the Tokenomics of Alephium ](https://medium.com/@alephium/tokenomics-of-alephium-61d59b51029c)

1. [Mining](#mining)
    - [What is the Mining Reward?](#what-is-the-mining-reward)
    - [I have GPU model XYZ, what is my profit per day?](#i-have-gpu-model-xyz-what-is-my-profit-per-day)
2. [dApps](#dapps)
    - [What are stateful UTXOs and how are they different from UTXOs that hold NFTs that represent state?](#what-are-stateful-utxos-and-how-are-they-different-from-utxos-that-hold-nfts-that-represent-state)
    - [Is anyone already building a DEX on ALPH?](#is-anyone-already-building-a-dex-on-alph)
    - [How efficient would ALPH be for a DEX?](#how-efficient-would-alph-be-for-a-dex)
3. [Wallet](#wallet)
    - [Is there a way to distinguish between a Bitcoin legacy address and an Alephium address?](#is-there-a-way-to-distinguish-between-a-bitcoin-legacy-address-and-an-alephium-address)
4. [Tokenomics](#tokenomics)
    - [If tokens are burnt, will there be a time in the future where the amount of existing ALPH will be close to zero?](#if-tokens-are-burnt-will-there-be-a-time-in-the-future-where-the-amount-of-existing-alph-will-be-close-to-zero)
    - [What is the minimum Transaction Fee (TF)?](#what-is-the-minimum-transaction-fee-tf)
5. [Miscellaneous](#miscellaneous)
    - [Why did you choose PoLW, not PoS?](#why-did-you-choose-polw-not-pos)
    - [Documents mention up to 10K TPS. Why do i see that we are currently way below 100 TPS?](#documents-mention-up-to-10k-tps-why-do-i-see-that-we-are-currently-way-below-100-tps)
    - [Why not have 1M shards?](#why-not-have-1m-shards)
    - [What is the difference between NEAR and Alephium?](#what-is-the-difference-between-near-and-alephium)

## Mining

### What is the Mining Reward?
Mining reward is a combination of the BR and TF. TF are bound to the market.

Let’s say Block Reward is BR and Transaction Fees are TF. The miner will get: 

`BR + min(BR, TF / 2)`

The first half of the Transaction fee will be burnt. Then the transaction fee is capped by the block reward. See dynamic calculator on this web-page.

You will find a more elaborate explanation of the Block Reward [in this article from the Official Alephium Medium](https://medium.com/@alephium/alephium-block-rewards-72d9fb9fde33)

### I have GPU model XYZ, what is my profit per day?
A community member has made a spreadsheet with different GPUs [availble here](https://docs.google.com/spreadsheets/d/10eUjwGU-Kmw1XM1dDOKfdscOeShakSnjcBGzBT46rmc/)

## dApps

### What are stateful UTXOs and how are they different from UTXOs that hold NFTs that represent state?
There are two type of states: mutable state (e.g. ETH) and immutable state (e.g. Extended UTXO). Mutable state is much more expressive as you can see from the ecosystem of ETH, while eUTXO can be used to build some applications with limitations. In our stateful UTXO model, we support ETH like mutable states. We could build Uniswap-like applications easily. [Here is a simple example](https://github.com/alephium/alephium/blob/master/app/src/it/scala/org/alephium/app/SmartContractTest.scala#L122-L153)

### Is anyone already building a DEX on ALPH?
We have a simple [Uniswap-like DEX in the test](https://github.com/alephium/alephium/blob/master/app/src/it/scala/org/alephium/app/SmartContractTest.scala#L142-L170)
We could also support order-book style DEX due to UTXO model, which could avoid the well known impermanent loss problem, but the order matching will be a new problem
We will build DeFi applications after mainnet, right now the focus is a stable and mature full node. Hopefully, we could attract some community team to work on DeFi applications. Our VM and language are dev-friendly. Developers familiar with Solidity could build similar application on Alephium

### How efficient would ALPH be for a DEX?
If you mean capital efficiency, that would depend on the design of DEX, similar to all the DEX apps on ETH. There are tradeoff for different projects.

As we are still early, it will take some time to get good liquidity. Also, we will need to build oracles based on CEX, which will take some time. But there is no technical block. And we could demonstrate the first practical DEXs on a sharded blockchain

## Wallet

### Is there a way to distinguish between a Bitcoin legacy address and an Alephium address?
Alephium addresses are usually longer, as it uses 32 bytes hash instead of 20 bytes hash.

## Tokenomics
 
### If tokens are burnt, will there be a time in the future where the amount of existing ALPH will be close to zero?
Theoretically yes, the future is not really projectable beyond 80 years. However it is not uncommon for open-source community-driven blockchains such as Alephium to change their policies along their evolution. If the community decides to alter a cap, then that cap will be altered.

### What is the minimum Transaction Fee (TF)?
Currently the minimum transaction fee is hard-capped at 0.00000000000001 ALPH. The pricing is however bound by auctioning and therefore dynamic. However we are investigating ways to alter the minimum TF dynamically based on hashrate.

## Miscellaneous

### Why did you choose PoLW, not PoS?
1. PoW is simple and robust. It's much easier to design sharding algorithm with PoW
2. PoS is not tested by time yet, we look forward to see how PoS will evolve after ETH's PoS switch
3. PoS tends to be more centralized, as you could see from the DeFi projects
4. PoS is more vulnerable to some DeFi attacks like MEV

### Documents mention up to 10K TPS. Why do i see that we are currently way below 100 TPS?

Let’s break it down in two parts: Estimation and actual Testing. 

**Estimation:** If we have N shards with 1 MB block size + 64 seconds block time, then the TPS would be N * 1024 * 2 / 64 assuming 0.5KB tx size. With 16 shards, we could reach 512 TPS (ultimately hard fork to 1024 shards, which would be >10K TPS). This would need quite some optimization in I/O and propagation, our full node is ready for 50, so 100TPS should definitely be fine. This is very normal, if you try BTC old version, it will not be able to sync actually due to performance issues. So old BTC version cannot support 7 TPS. It also took ETH a long journey to make it efficient enough to support the current TPS.
 
**Testing:** High TPS testing for UTXO-based blockchain is not easy, because for each tx injection epoch a lot of UTXOs have to be kept. Right now, we have tested 5TPS, but keep in mind that we send all these TXs in one batch every minute. We could do this every several seconds, then we could definitely achieve more than 100TPS. It will need more time to improve the testing bots, which is not a very high priority right now. 
 
Etheirway, it is not possible to expect the full node to be fully optimized when the mainnet is launched. Down the line when the network grows mature and large enough, the plan is to hard fork to support 32 groups and 1024 shards. With 1024 shards, it could reach >10K TPS for sure. However, it will be a long journey to go there. Technically, probably 1-2 years of improvements and optimizations. Economically, we need the network to grow large enough so there is a demand for us to hard fork to so many groups. Note that we have already successfully run a simulation, with 1024 shards where we did not validate the inputs (as to not need to maintain a real UTXO set). 

### Why not have 1M shards? 
The groupsize G is not very big. Each node needs to maintain 2G - 1 other shards for consistency. We want to keep things small. 2G-1 cannot be too large. Given the average network bandwidth is enough, G can be set as high as 32. There are some computation overhead as well, but networking is the main bottleneck to push G higher.

### What is the difference between NEAR and Alephium?
- We have 16 shards on mainnet, while NEAR's sharding [is working in progress.](https://near.org/blog/near-launches-simple-nightshade-the-first-step-towards-a-sharded-blockchain/)
- We believe that PoW is a better approach for decentralized layer one protocol, while NEAR is PoS
- ALPH is based on the UTXO model, and NEAR is based on the account model. UTXO model for DeFi is a growing tech, which has great potential for secure DeFi
- NEAR is more mature in terms of ecosystem, as it's  launched much earlier than ALPH. ALPH is just launched 1-month ago

### WHEN MOON?
1ALPH always amounts to 1ALPH. The journey is the destination!
