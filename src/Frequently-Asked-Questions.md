# Frequently Asked Questions

Before diving in, we recommend that you check the following ressources as they provide useful information about Alephium: 

- [Official Website](https://alephium.org)
- [Official Medium](https://medium.com/@alephium), specifically: 
    - [Alephium's Tokenomics](https://medium.com/@alephium/tokenomics-of-alephium-61d59b51029c)
    - [Alephium's Block Rewards](https://medium.com/@alephium/alephium-block-rewards-72d9fb9fde33)
    - [Alephium's Community Reward Program](https://medium.com/@alephium/introducing-community-rewards-f4638bbf14bf)
    - [Alephium's Q1 2022 Update](https://medium.com/@alephium/alephium-q1-project-update-50f4a7b354b0)
    - [Alephium's 1st AMA](https://medium.com/@alephium/alephiums-first-live-ama-761a90d3f672)

FAQ 

1. [Mining](#mining)
    - [What is the Mining Reward?](#what-is-the-mining-reward)
    - [I have GPU model XYZ, what is my profit per day?](#i-have-gpu-model-xyz-what-is-my-profit-per-day)
    - [What is the reason to hold the block reward for 500 minutes, given the block time is only 64 seconds?](#what-is-the-reason-to-hold-the-block-reward-for-500-minutes-given-the-block-time-is-only-64-seconds)
    - [Why do I have 4 mining addresses ?](#why-do-i-have-4-mining-addresses-)
2. [dApps](#dapps)
    - [What are stateful UTXOs and how are they different from UTXOs?](#what-are-stateful-utxos-and-how-are-they-different-from-utxos-that-hold-nfts-that-represent-state)
    - [Is anyone already building a DEX on ALPH?](#is-anyone-already-building-a-dex-on-alph)
3. [Wallet](#wallet)
    - [Is there a way to distinguish between a Bitcoin legacy address and an Alephium address?](#is-there-a-way-to-distinguish-between-a-bitcoin-legacy-address-and-an-alephium-address)
4. [Tokenomics](#tokenomics)
    - [If tokens are burnt, will there be a time in the future where the amount of existing ALPH will be close to zero?](#if-tokens-are-burnt-will-there-be-a-time-in-the-future-where-the-amount-of-existing-alph-will-be-close-to-zero)
    - [What is the minimum Transaction Fee (TF)?](#what-is-the-minimum-transaction-fee-tf)
5. [Miscellaneous](#miscellaneous)
    - [Why is the project named Alephium?](#why-is-the-project-named-alephium)
    - [Why did you choose PoLW, not PoS?](#why-did-you-choose-polw-not-pos)
    - [Documents mention up to 10K TPS. Why do i see that we are currently way below 100 TPS?](#documents-mention-up-to-10k-tps-why-do-i-see-that-we-are-currently-way-below-100-tps)
    - [Why not have 1M shards?](#why-not-have-1m-shards)


## Mining

### What is the Block Reward?

Alephium’s block reward is made up of two components: the reward for newly generated blocks, also called Mining Reward (MR), and Transaction Fees (TF). 

Total Block Reward = Mining Reward + min(max(MR, 1 ALPH), Transaction Fee / 2)

You will find a more elaborate explanation of the Block Reward [in this article from the Official Alephium Medium](https://medium.com/@alephium/alephium-block-rewards-72d9fb9fde33)

### I have GPU model XYZ, what is my profit per day?
A community member has made a spreadsheet with different GPUs [available here](https://docs.google.com/spreadsheets/d/10eUjwGU-Kmw1XM1dDOKfdscOeShakSnjcBGzBT46rmc/)

### What is the reason to hold the block reward for 500 minutes, given the block time is only 64 seconds?

The 500min lock was implemented to prevent re-org attacks. Similarly to Bitcoin, which has ~1000 minutes lock for mined rewards.

### Why do I have 4 mining addresses ?

Alephium is a sharded blockchain with G groups and G*G shards. Due to this design, it is necessary to have one mining address per group. 

On the mainnet, we currently have 4 Groups and 16 shards, which is why you have 4 mining addresses. One for each group

## dApps

### What are stateful UTXOs and how are they different from the other UTXOs models?
There are two type of states: mutable state (e.g. ETH) and immutable state (e.g. UTXO, Extended UTXO). Mutable state is much more expressive as you can see from the ecosystem of ETH, while eUTXO can be used to build some applications with limitations. 
In our stateful UTXO model, we support ETH-like mutable states. It allows us to easily build dApps as powerful as on Ethereum without the security concerns of the account model. 

### Is anyone already building a DEX on ALPH?
We have a simple [Uniswap-like DEX in the test](https://github.com/alephium/alephium/blob/master/app/src/it/scala/org/alephium/app/SmartContractTest.scala#L142-L170)
We could also support order-book style DEX, which would avoid the well known impermanent loss problem thanks to the UTXO model. 

We identified DeFi and dApps to be the next critical focus for Alephium. To kickstart the development we will build clean Proof-of-concept dApps, to serve as examples. This will help us find bottlenecks or edge cases we haven’t been able to identify before. It will also serve as a basis to compile the necessary documentation to help community developers to build and deploy their applications. 
Our VM and language are really dev-friendly and if you're familiar with Solidity, you can easily build similar application on Alephium.

## Wallet

### Is there a way to distinguish between a Bitcoin legacy address and an Alephium address?
Alephium addresses are usually longer, as it uses 32 bytes hash instead of 20 bytes hash.

## Tokenomics
 
### If tokens are burnt, will there be a time in the future where the amount of existing ALPH will be close to zero?
Theoretically yes, the future is not really projectable beyond 80 years. However it is not uncommon for open-source community-driven blockchains such as Alephium to change their policies along their evolution. If the community decides to alter a cap, then that cap will be altered.

### What is the minimum Transaction Fee (TF)?
Currently the minimum transaction fee is hard-capped at 0.00000000000001 ALPH. The pricing is however bound by auctioning and therefore dynamic. However we are investigating ways to alter the minimum TF dynamically based on hashrate.

## Miscellaneous

### Why is the project named Alephium? 

For those of you less familiar with set theory and mathematics the origin of the name “Alephium” might not be so evident. It is made from the name “Aleph” which is defined on wikipedia: “Aleph numbers are a sequence of numbers used to represent the cardinality of infinite sets that can be well-ordered. They were introduced by the mathematician Georg Cantor and are named after the symbol he used to denote them, the Hebrew letter aleph ( ℵ )”

In fact, the logotype for Alephium is a stylisation of the letter Aleph. 

In an homage to the technical promises of Ethereum, we followed the same naming pattern and the name Alephium was coined.

### Why did you choose PoLW, not PoS?

Blockchain technology is still at an early stage and one of the most prevalent questions is: what blockchain infrastructure is needed for the next 10 years for Dapps, including DeFi ?

We believe need a blockchain that is scalable with high throughput and low transaction fees. We want a high level of programmability like on Ethereum. And we need it to be as reliable and secure as Bitcoin is.  
As a result, Alephium was developed on the idea to build a scalable Bitcoin with a reliable DeFi solution.

According to the Lindy effect’s theory, and despite POS recent successes, it’s very likely that  the Bitcoin model and  sharding + PoW is still the most robust and decentralized way to build a scalable blockchain. Specifically:

1. PoW is simple and robust. It's much easier to design sharding algorithm with PoW
2. PoS is not tested by time yet, we look forward to see how PoS will evolve after ETH's PoS switch
3. PoS tends to be more centralized
4. PoS tends to reduce trustlessness as the cost of running a node can be significantly higher
5. PoS is more vulnerable to some DeFi attacks like MEV

### Documents mention up to 10K TPS. Why do i see that we are currently way below 100 TPS?

Let’s break it down in two parts: Estimation and actual Testing. 

**Estimation:** If we have N shards with 1 MB block size + 64 seconds block time, then the TPS would be N * 1024 * 2 / 64 assuming 0.5KB tx size. With 16 shards, we could reach 512 TPS (ultimately hard fork to 1024 shards, which would be >10K TPS). This would need quite some optimization in I/O and propagation, our full node is ready for 50, so 100TPS should definitely be fine. This is very normal, if you try BTC old version, it will not be able to sync actually due to performance issues. So old BTC version cannot support 7 TPS. It also took ETH a long journey to make it efficient enough to support the current TPS.
 
**Testing:** High TPS testing for UTXO-based blockchain is not easy, because for each tx injection epoch a lot of UTXOs have to be kept. Right now, we have tested 5TPS, but keep in mind that we send all these TXs in one batch every minute. We could do this every several seconds, then we could definitely achieve more than 100TPS. It will need more time to improve the testing bots, which is not a very high priority right now. 
 
Etheirway, it is not possible to expect the full node to be fully optimized when the mainnet is launched. Down the line when the network grows mature and large enough, the plan is to hard fork to support 32 groups and 1024 shards. With 1024 shards, it could reach >10K TPS for sure. However, it will be a long journey to go there. Technically, probably 1-2 years of improvements and optimizations. Economically, we need the network to grow large enough so there is a demand for us to hard fork to so many groups. Note that we have already successfully run a simulation, with 1024 shards where we did not validate the inputs (as to not need to maintain a real UTXO set). 

### Why not have 1M shards? 
The groupsize G is not very big. Each node needs to maintain 2G - 1 other shards for consistency. We want to keep things small. 2G-1 cannot be too large. Given the average network bandwidth is enough, G can be set as high as 32. There are some computation overhead as well, but networking is the main bottleneck to push G higher.

### WHEN MOON?
1ALPH always amounts to 1ALPH. The journey is the destination!
