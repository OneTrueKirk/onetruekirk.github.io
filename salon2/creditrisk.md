# Creating a Credit Risk Framework for DeFi
## Subnmitter: Jalil Farid

This is a peer review article as part of the second Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This article is reviewing an article by [Jalil](https://twitter.com/digital_monad
) exploring credit risk analysis in a DeFi context. See the full submission [here](http://jfarid27.github.io/2024/01/26/risk-parameter-estimation-areh-202401260841.html).

Blurb from author:

>The document provides an in-depth analysis of risk parameter estimation in crypto markets, focusing on the unique challenges of decentralized finance and proposing advanced methodologies for effective risk management. It concludes with actionable recommendations for improving lending practices and suggests areas for future research to enhance the stability and security of crypto lending platforms.

## Rates and Risk

This article is an excellent introduction to risk analysis, and also complements [Yaron's SmartLTV paper](https://onetruekirk.github.io/salon2/smartltv.html). While the SmartLTV system prioritizes avoiding insolvency, Jalil's article instead asks "how can we most accurately measure risk in order to set an interest rate that is +EV"? After all, there is no such thing as a market with zero risk of loss, and instead of a simplified onchain calculation, we can perform nuanced offchain estimation to determine an optimal target rate.

The dominant DeFi lending markets use a utilization based interest rate framework, where the rate is adjusted to maintain a target liquid reserves fraction. The problem with this is that it often fails to correctly price risk. It's entirely possible for borrowing demand (and interest rate) to be low, but risk to be high.

An obvious step is making interest rates LTV-sensitive, which Jalil describes in the following passage:

>In traditional finance, risk tranches have lots of historic precidence where a user’s assets may be contractually sold off in chunks if price targest are hit, but a closed form model is just to take partitions of the users assets, and assert specific LTV requirements for each tranche.
>
>While tranched lending isn’t particularly complex, one could imagine for a system with a new type of collateral and a target lending cap, to partition the cap into “chunks” with ranked LTV, where higher LTV commands higher payment rates. As capacity is reached on lower LTV (with cheaper rates), it is assumed the market would reach an equilibrium where most of the capacity with higher LTV is un-utilized. This particular system of course requires maintenance of lending rates and creation of new buckets as some risk tranches may be auctioned under high collateral stress, but serves to help protect lenders from a shock and major loss in a single lending agreement.

There is precedent for this model in DeFi as well, with MakerDAO long maintaining multiple ETH vault types with different collateralization ratios and interest rates.

This reminds me of [Ajna](https://ajnafi.com), which has user-determined price tranches instead of a trusted price oracle, and also reflects the design of the Credit Guild, which can have an effectively unlimited number of lending terms for a given collateral asset.

## Crypto-equity

Besides purely reactive risk models based on market data, it is also possible to engage in fundamental analysis of assets. Token emissions schedules, associated cash flows, and investor unlocks are all highly relevant to appropriate LTV and interest rates. The importance of any one of these factors is subjective, making them impossible to encode in a neutral smart contract.

As Jalil notes, traditional cash flow valuation models don't work well for cryptoassets:

>Many cryptocurrencies can be argued as both an equity premium that sells a commodity, or a commodity itself that is used to refine other (financial) products. These difficulties make the models of using traditional equity risk frameworks suspect since these systems sit somewhere between cashflow generating organizations, and simple information systems.

Early in the design of the Credit Guild, I wanted to use a RAI-like controller to manage interest rates. The irreducible complexity of risk analysis is what led us to build a system centered around regulating the behavior of active lenders (ensuring skin in the game, enforcing appropriate timelock delays and so on). The body of active lenders will produce a market outcome which may or may not prove accurate to an asset's real risk. Over time, analysis will become more sophisticated, and more historical data will become available, so efficiency should generally improve.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>