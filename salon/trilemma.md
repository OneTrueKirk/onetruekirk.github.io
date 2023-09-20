# "The Stablecoin Trilemma" Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This post is reviewing [an article on the "stablecoin trilemma"](https://fortunafi.beehiiv.com/p/the-stablecoin-trilemma) submitted by [Nick Garcia](https://twitter.com/thecurious_gark) of Fortunafi.

## When life gives you lemmas

The phrase "stablecoin trilemma" is inspired by the blockchain scalability trilemma articulated by Vitalik Buterin, which describes an unavoidable tradeoff between scalability, security, and decentralization in blockchains. Likewise, the stablecoin trilemma proposes a tension between capital efficiency, stability, and decentralization.

Let's start with the part of the article I like the best:

>Decentralization at the protocol level to allow stablecoin protocols to offer greater utility than those with a centralized model. Because decentralization only scales with a highly efficient governance system, decentralized stablecoins should optimize for a governance model that enables operational efficiency.
>
>To truly scale, decentralized stablecoins must incorporate native digital assets & on-chain real world assets and drive value to users by offering highly competitive yields. Given that demand for stablecoins is greater than the supply of high-quality native digital assets, the best decentralized stablecoins will need to attract the highest quality collateral on-chain and off-chain.
>
>A decentralized stablecoin that wants to maintain stability (while also being backed by on-chain and off-chain collateral) must be capable of ensuring transparency around asset liability management while also being capable of trustlessly valuing all balance sheet assets to validate liquidity & solvency.

I believe this hits the nail on the head -- there is tremendous room for improvement in governance. Slow, monolithic, one size fits all governance is out, granular, responsive, incentive aligned governance is in. The GHO Facilitator model and Maker SubDAOs are an attempt at this, in the same vein as Tribe DAO [governance pods](https://tribe.fei.money/t/fip-82-governance-enhancements/3945). While I'm skeptical of subDAOs with their own liquid token that is used for emissions, this model is broadly an improvement to having only a single level of governance. In the Ethereum Credit Guild, you could say that each governance token holder is their own subDAO, with a discrete amount of power to allocate CREDIT.

## Negative capital efficiency

This passage troubles me :

>Because stablecoins are supposed to maintain a $1 peg, it’s essential to consider how much money has to go into a stablecoin system to get back $1 worth of tokens. If it costs $1 to get $1 worth of tokens, a stablecoin has a capital efficiency of 1 ($1 out / $1 in). However, suppose a $1 peg can be achieved and maintained with only 90% of its backing coming from fiat stablecoins. In that case, the stablecoin is considered 10% more capital efficient with a capital efficiency of 1.11 ($1 out / $0.9 in). If a stablecoin is capital efficient, its advantages often come at the cost of stability (undercollateralized) or centralization (1:1 collateralized).

I've written elsewhere about why endogenously collateralized or undercollateralized stablecoins [cannot succeed](https://onetruekirk.github.io/chrysopoeia.html) at scale or over long periods of time. It's not possible to take $0.50 and make it worth $1 with any amount of fancy math. It's not possible to ensure that a native asset backstop like LUNA is always worth enough to back each stablecoin with $1. We can make a stronger statement than "this type of system hasn't succeeded yet", and instead assert that **there is no such thing as greater than 100% capital efficiency in stablecoin issuance**.

## Decentralization vs scalability

Capital efficiency *is* a meaningful and important concept, in that a lending market that offers lower collateral requirements will likely attract more borrower demand. There *is* a tradeoff between backing exclusively with like kind assets 1:1 vs overcollateralized interest paying positions. There is *not* any possibility of issuing a $1 stablecoin using less than $1 in collateral.

That means that if you *only* want a stablecoin for its stable value, ie, if you are denominating your debt in it, you'll tend to prefer fiat stablecoins. If you care about yield, you'll prefer stablecoins with quality yield bearing RWA backing, while if you care mostly about censorship resistance, you might be willing to pay a premium for a stablecoin backed mostly by ETH. Yield isn't part of the trilemma as articulated, but it exists in the tradeoff space, in tension with decentralization and aligned with scalability.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>