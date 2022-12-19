# A Farewell to Arbitrum

Today Volt Improvement Proposal 13 deprecated support for VOLT on Arbitrum. Holders will be able to redeem with no slippage or fees, but the Arbitrum PSM price will no longer adjust based on the VOLT rate. [Read more in the community forum.](https://community.voltprotocol.io/t/vip-13-deprecate-arbitrum-support/21/9?u=onetruekirk)

It was regretful to me to roll back support for VOLT on Arbitrum after a four month experiment. This article is intended to address the reasoning behind VIP 13 in greater length, and explore what the future of VOLT on L2 might look like.

## Complexity Kills

This is the number one reason behind deprecating Arbitrum VOLT. As we proceed further in the market governance/ Volt 2.0 design process, it's become clear that multiple standalone instances of the system with separate state introduce too much complexity to safely reason about in this early stage. Any small mistake in smart contracts can be disastrous, and  [bridges](https://rekt.news/bnb-bridge-rekt/) are [known](https://rekt.news/nomad-rekt/) to be [especially](https://rekt.news/wormhole-rekt/) [dangerous](https://rekt.news/harmony-rekt/).

A protocol like Uniswap doesn't have to worry about this much, since there are no interactions needed between Uniswap v3 on mainnet and Uniswap v3 on Arbitrum. Things are much different for any application making use of an oracle, or where cross chain state matters.

## Liveness Risks

Possibly the scariest risk of L2s today is liveness failure. What happens if the Arbitrum sequencer goes down and no transactions can be completed? There's a mechanism by which transactions can be "[force included](https://developer.offchainlabs.com/sequencer" after about 24 hours. That means that worst case, any lending market on Arbitrum could experience 24 hours in which liquidations are impossible.

Even accidental downtime during a period of high volatility can thus represent risk. In the case of Volt Protocol, we might see a deviation in the PSM price between L1 and L2, exposing the protocol to losses via arbitrage. While there are ways to manage this risk, such as charging a spread on L2 VOLT mint and redeems equal to the daily VOLT rate, the example is illustrative of the risks of cross layer operation.

The situation is worse for something like a lending market or perpetuals platform, where bad debt may accrue during downtime, or users may find themselves liquidated when the sequencer comes back online who would otherwise have been able to secure their positions and avoid additional fees.

## The Dark Forest

In [September 2021](https://medium.com/offchainlabs/arbitrum-one-outage-report-d365b24d49c), the sequencer was down for about 45 minutes. According to Offchain Labs:

>The root cause of the downtime was a bug causing the Sequencer to get stuck when it received a very large burst of transactions in a short period of time.

Was this a natural surge in activity or something more sinister in the dark forest?

A determined attacker could potentially bring down the sequencer on Arbitrum or other rollup for a period of time. This type of attack was attempted against the Ethereum network and failed in the end, though they impacted the network over more than a week. Even in 2016 Ethereum had a large number of miners in comparison to the centralized sequencing of rollups today.

## Rollup Liquidity Crises

Optimistic rollups have withdrawal delays to provide a window for fraud proofs. [Read here for a good introduction to optimistic rollups](https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/).

Bridge protocols facilitate faster exits for users, but only to the limits of their available liquidity. If a large number of users want to exit in a short time, they can get stuck on L2.

It's easy to say "that's their problem", but that may not hold true in the case of cross layer systems. For example, what happens if there is a large demand by SNX stakers to repay their debt positions (let's say enough to cause a 25% sUSD supply drawdown), but half the sUSD is on Optimism? There's risk of upward depeg in this scenario. DAI is protected from this issue by the PSM, but Liquity's LUSD may also be exposed to the same risk with about 10% of the supply currently on Optimism.

Generally, **any stablecoin without PSM minting that is generated as debt on L1 but has a decent portion of the supply on L2 will be vulnerable to upward depeg under some conditions**.

## Zero Knowledge

The perils of optimistic rollups mostly come down to the fact that they fragment the state, and it's impossible to guarantee synchronous states on the two layers. This introduces substantial design complexity around managing a multilayer system.

The alternative is a zk rollup [like Aztec](https://docs.aztec.network/how-aztec-works/aztec-connect) that uses L1 state, and so does not require separate contract logic. Unlike an Optimistic rollup, this brings up a chicken and egg problem where cost savings are possible only with batching *per application*.

What does this mean?

On Arbitrum, if one user wants to mint VOLT and another wants to sell ETH, they both enjoy cost savings compared to mainnet. On a zk rollup that uses mainnet state like Aztec, these users won't save any money (though they will benefit from privacy). However, if both of them want to mint VOLT, each will pay only half as much in transaction cost.

This is elegant in that it scales up DeFi applications in proportion to their usage demand. It also implies that integration will be most beneficial when VOLT protocol reaches a certain scale of transaction demand High demand contracts like major Uniswap pairs are a more obvious early candidate for this style of scaling.

## App rollups?

An app-specific zk rollup might be a reasonable long term direction for the most successful DeFi applications. With no delay to withdraw funds, it's easy to provide a home for small users while remaining connected to the flows of funds on L1. In most cases, it's probably overkill, and there will be a simpler way to minimize (or internalize) MEV.

In [Unichain](unichain.md), I contemplated the possibility of an application specific rollup for Uniswap. Now, I'm wondering where to even draw the line between a zk rollup that shares mainnet state and a normal mainnet contract. It seems like there is a spectrum from a naive mainnet contract that defers entirely to the Ethereum protocol for execution, to a system with advanced features like MEV auction or batching for small users (liquidations an example of the former, VOLT PSM is an example of the latter), to general execution batching system like Aztec (also with value add features like privacy), and finally to an application with complete execution functionality (its own internal rules for ordering any transactions that affect its state).

## The absolute state

So far we've discussed optimistic rollups vs zk-rollups which keep their state on mainnet. The future is wilder however, as there also exists the possibility of keeping state offchain, and only posting succinct proofs on chain. This concept is known as a [Validium](https://ethereum.org/en/developers/docs/scaling/validium/).

In a sense, this gives you the best of both worlds of a zk rollup and an optimistic rollup, with no need for a fraud proof window (on-demand withdrawl) like zk rollups, but comparable or even lower tx costs than optimistic rollups.

On the other hand, because no state data is posted to mainnet, separate instances of system contracts are needed (unlike Aztec or similar products), so there is additional complexity and overhead for developers.

## too long, didn't read

I'm still working to understand the limitations of layer two scaling in more detail to inform Volt Protocol's future directions. The state fragmentation and withdrawal delays of optimistic rollups make them dangerous for cross-layer systems. Zk rollups are promising but more expensive and less scalable for protocols with less transaction demand. Validiums are intriguing but probably remain a ways off.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>