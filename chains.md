# long united, the empire must divide
> on why we need new blockchains

![img](romance.jpg)

Why do we need *yet another* new blockchain or layer two network? What's the point of Unichain? Can Monad compete with Solana?

Until quite recently I took a chain minimalist view. A chain with well established DeFi protocols, deep liquidity, and a history of quality execution seems infinitely preferable to an upstart.

There are two main factors that have changed my perspective:

1. The monolithic age has ended. Stablecoin issuers have proven willing to rapidly support new chains, RWA tokenizers are agnostic to distribution routes, the quality and diversity of bridges and oracles continues to improve. We're fast reaching the point where the same assets and infrastructure are available on dozens of chains.

2. The institutions are not coming -- they're here. The network effect of existing DeFi pales before Coinbase ($220B AUM), let alone Blackrock ($10T AUM). For these players, all of the following are comparably important to existing liquidity network effects:
    * brand power
    * optimizing for their specific usecase (throughput, uptime, etc)
    * captive markets (keeping users in their ecosystem, focused on their assets)

This does **not** mean that liquidity network effects are irrelevant. Listing an asset on a lending market or decentralized exchange with deep existing liquidity remains a key goal for new issuers.

That being said, my long-term view has shifted from "the winning blockchain will house 80%+ of stablecoin and DeFi TVL" to "blockchains will follow a similar TVL distribution to banks' AUM", meaning there will be one clear leader, but with 1.2x to 2x the TVL of the second place, not 10x.

## categories to watch

There are three main categories of new chain that strike my interest from a DeFi perspective:

1. **asset-type specific** chains. This includes *Bitcoin rollups*, which prioritize minimizing trust assumptions for BTC holders who wish to use DeFi applications, *RWA chains* that offer first-class support for asset tokenization, and *payments chains* which canonize a stablecoin and even use it to pay for network txs instead of a native token.

2. **brand chains**, created by financial institutions with powerful existing network effects in order to offer new use cases to their users without letting them out of their walled garden. Generally combined with other tooling like smart wallets and branded tokenized assets, Base being the prime example.

3. **high-performance chains**, not mutually exclusive with the prior categories, but notable for their compromises on various risks (liveness, centralization) to acheive hyperscale while preserving at least *some* of the value propositions of decentralized blockchain networks. These chains offer the only way for blockchain networks to truly compete with TradFi trading venues. Their defining shared characteristic is a *limited validator/sequencer set*, essential to acheive high performance. The risks this entails can be compensated for by various means, such as economic security, fallback consensus mechanisms (in case of liveness failure), zk verification, and the familiar optimistic rollup challenge period.

Separate from these categories, there are a few notable architectural innovations that are unlocking new spaces in network design:

1. Strong interoperability (such as Polygon AggLayer, Superchain interop), allowing customized consensus models to more easily share state

2. Data availability sampling, allowing reliable data storage and light client operation without every node retaining the full historical state

3. The rise of zk verification (which is leading towards hardware-acceleration) allowing specialized nodes to push the boundaries on performance without taking on strong trust assumptions

## conclusion

My core takeaway from this thinking is that **no chain can be the best at everything**, and that while we should expect to see a clear winner in each dimension, it is very difficult to predict which this will be, or which category the market will decide is the most important.

From a DeFi builder perspective, this means it is wise to be chain agnostic and to go where the users and unique use cases are.

From an investing perspective... well, I can't help you there.

## obligatory disclaimer

Everything in this article is my personal view and does not represent an official stance of Morpho Labs or the Morpho Association.