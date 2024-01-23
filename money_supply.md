# The Money Supply
*why fixed-supply or deflationary assets don't make good money*

AND

*how to think about the "right" money supply growth rate*

## What is money?

For the purposes of this article, *money* refers always to the *base money*. Under a gold standard, that is physical gold, even if most people transact using banknotes or digital balances. Under the fiat currency regime, that is government debt (the total supply of government-issued notes, including both zero-interest currency and yield bearing notes with a defined maturity).

## What is money good for? What makes a good money?

Money is used to exchange one good or service, produced at a specific place and time, for another good or service produced at a different time and place. People who have a coincidence of wants might trade (directly swap goods and services) -- for anything else you need money.

This implies a few desirable properties for money:

* it should be easily movable to different places
* it should be easily divisible into arbitrarily small or large sizes
* its value should be consistent over time
* it should be difficult to counterfeit

None of these properties are absolute -- there is always some cost to transport or swap, some limit onto how small or large a purchase is feasible with a given type of money, and some volatility in the value of any substance.

It's clear from looking at these properties why precious metals were used as money. They are durable, have a cost of production, can be divided into small units. The use of standard units (coins of known weights) makes it easier to check if a given coin is really gold or silver as claimed, by comparing it to a sample of known validity.

The difficulty of transporting precious metals over long distances, the risk of storing large quantities, as well as the need to make either small or very large purchases that are impractical using metal, all contributed to physical metal being replaced by paper notes backed by the same. This transition was **driven by market demand**.

The removal of the gold backing and shift to fiat money, on the other hand, was not market driven, but **rather forcibly imposed on markets by state power**. We can confidently state that paper notes, and now digital money, are superior for transactions than physical gold coins, but not that fiat backing has better monetary properties than gold.

## BTC isn't good money
*and neither is ETH. not enough to go around*

I own both ETH and BTC, but don't use either as money. They have a few things going for them as exchange media:

* easily sendable to anyone
* divisible into very small units
* impossible to counterfeit

However, they suffer from one glaring weakness which precludes their adoption as money, which is that the supply cannot be expanded to meet demand. Unlike gold, where a durable increase in demand will lead to increased production, there is a hard cap on the BTC supply, while ETH will likely be deflationary in the long term like a corporation conducting share buybacks.

This means that given an increase in demand, price must go up. Sounds good, right? Maybe for us holders, but not for anyone actually trying to use these assets as money. Sudden and durable price increases would be absolutely ruinous for anyone denominating debts in BTC or ETH. Imagine if a majority of mortgages in a given country were BTC denominated, and then the price rose 50% over two years. Even for short term pricing, the volatility of cryptoassets is too high for convenience.

## Fiat Can Be Good Money, But Requires Trust

Fiat can have arbitrary supply characteristics. [Much](https://mises.org/library/less-zero-case-falling-price-level-growing-economy-0) [has](https://www.amazon.com/Floored-Misguided-Experiment-Prolonged-Recession/dp/1948647087) [been](https://www.amazon.com/dp/0691003548?tag=fivebooks001-20) [written](https://oll.libertyfund.org/title/bagehot-lombard-street-a-description-of-the-money-market) about the optimal inflation target for a central bank as well as what interest rate it should target under ordinary and emergency conditions. If well managed, the supply characteristics may be desirable. The problem is that the One Ring corrupts -- it is too tempting for the state to use control over money as both a funding source and a weapon. The tendency will always be for government debt to expand faster than the market's demand for money, abusing the seignorage power to fund expenses.

## Digital Gold

Gold is better than fiat because the supply is expandable, but only within hard physical limits. This protects savers from extreme inflation, while also shielding shielding borrowers from extreme price increases. The cost of mining gold is determined by the advancement of technology, the availability of labor, energy costs, and by how much gold has already been mined, since the more accesible reserves are depleted first. If demand is sufficient, it will be mined from the sea floor and from asteroids one day. This means that the cost to mine more gold is **correlated to energy and labor costs**.

To create a digital asset with the desirable supply properties of gold, we might modify Bitcoin such that the mining difficulty slowly increases with each unit mined, and the block reward remains fixed. With a cost of production that steadily increases in compute terms, the actual production would be determined by the advance of technology (which tends to increase compute availability), energy costs, and by demand. If there is a decline in demand, the market price may drop below the cost of production such that mining ceases.

## Supply is not Demand

Despite its desirable supply characteristics, the asset we've described above has no inherent value, and it's difficult to determine how to effectively bootstrap its usage. The conditions of Bitcoin's adoption cannot be replicated, and even if they could, there is an inherently speculative aspect to its adoption today that conflicts with our desire to create a neutral, stable money.

If we put on our rose-colored glasses for a moment, we can envision a nation-state choosing to commit to a credibly neutral money supply that runs on a public ledger. Let's say that the initial cost of production is X units of electricity per Y coins produced, and that the cost of production goes up by Z for each coin produced. For the sake of argument, let's call this asset a neutral money unit, NMU.

The nation-state can pre-mine NMU corresponding to the existing circulation of its physical fiat currency, and back it 1:1 based on current market price, effectively pegging their existing currency to NMU. Note that they do not need to expend proof of work mining costs to create this starting supply. Only the production of future supply must be constrained by a known cost. With new bond issuances denominated in NMU, there is a known floor cost of repayment. Of course it's still possible for the government to make bad investments, see tax revenues decline vs interest costs, and ultimately default, but it can no longer silently debase the currency, since it is pegged to NMU instead of a free floating fiat regime. In the future, if demand to hold money grows, it can be met by the production of additional NMU denominated notes, rather than engaging in wasteful proof of work mining. The ability to mine functions as a **guarantee of cost of final settlement**, but is not desirable as the primary mechanism of meeting demand for money substitutes. Again, this is very like how things work under a mature gold standard where a central bank and government debt fill major economic roles.

Each nation can create its own NMU, and create a starting supply corresponding to its existing currency circulation. This allows them to use a credibly neutral base money within the country, without needing to decide on a **globally neutral initial supply distribution**. Gold is good in this regard because its physical distribution on the planet is essentially random. The concentration of supply of assets like BTC and ETH is a major obstacle to any future adoption as money. Price divergences between different nations' NMUs will reflect (and ultimately correct) trade imbalances.

## Proof of concept

A nation-state has an ability to generate demand that companies or protocols cannot compare to. However, an NMU can still be used in a lending market as an internal unit of account to reduce custodial risk. One can imagine an ETH-only lending market like Liquity or Reflexer, but instead of using a USD peg (whether hard or floating) for the debt asset, it is pegged to an NMU with a PSM. By defining a minimum cost in proof of work terms for borrowers to repay, and appropriately configuring collateral factors, a stable value can be created even without USD backing in the PSM. Unlike RAI, which can **only** be minted by those taking leverage, and thus must impose negative rates when holder demand is too great, NMUs can be produced using proof of work. This means that if holder demand exceeds borrower interest, there is a relief valve -- miners meet the excess demand and so there is no need for negative rates.

When I have this idea properly refined (for example, how much should the mining difficulty increase with each unit produced?), I'd like to test this in an instance of the [Credit Guild](https://credit-guild.gitbook.io/introduction/), as well as in some other markets like Ajna and Morpho Blue.

Please note that this concept is a draft and will be actively revised. Your thoughts are appreciated either in the comments or elsewhere.


<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>