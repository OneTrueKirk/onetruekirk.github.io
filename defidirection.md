# The Next Four Years of DeFi

As we look to scale VOLT, I spend a lot of time thinking about what DeFi lending markets and yield assets look like in the coming years.

## Contents

[Crypto-Secured Lending Yields Trend Down](#crypto-secured-lending-yields-trend-down) ETH is the best collateral

[Beyond Immediate Liquidatability](#beyond-immediate-liquidatability) you can't have your cake and eat it too

[Challenges of New Backing Types](#challenges-of-new-backing-types) why everyone needs a bigger surplus buffer

* [When Is Enough Enough?](#when-is-enough-enough) surplus buffer & illiquid backing

[DeFi Devours Tradfi Repo](#defi-devours-the-reposecured-lending-markets) the institutions are coming

[Dollar dominance continues to increase](#dollar-dominance-continues-to-increase)

* [ETH is money?](#alternative-denominations) it has to start somewhere

[DeFi certificates of deposit](#defi-certificates-of-deposit) stablecoin issuers want to borrow at fixed rates

## Crypto-Secured Lending Yields Trend Down

One of my early DeFi teachers and interlocutors was [Samuel Shadrach](https://samueldashadrach.github.io/Crypto/), who insisted against my naive objections that DeFi rates, then soaring beyond the furthest Heaven, must come crashing down to Earth. I thought that at the time that while DeFi summer yields were unsustainable, an on chain premium for capital made some sense.

It's since become clear to me that SS was right -- setting aside ephemeral, greater-fool token emissions schemes, the demand to borrow permissionlessly against cryptoassets like ETH, while substantial, cannot be expected to support consistently high rates.

On the contrary, a collateral that is easy to price and easy to liquidate in always online markets should command a low cost of credit. Long term, there should be a substantial discount to tradfi rates like the SOFR given there is no "overnight" risk in an always-online market. Lending against overcollateralized cryptoasset positions may well be the safest and most liquid yield opportunity available in the world, and so the yields won't be very high.

Lending markets become increasingly competitive, with more capital seeking returns and technological improvements. Morpho reduces the price for borrowing DAI on Aave from 1.67% -> 1.09%. MakerDAO is now offering *free* borrowing against stETH in an attempt to gain market share.

From the perspective of Volt Protocol, lending in a market like Compound or Aave, or an in-house lending market in the future, is "cashlike", reserves that can be readily called upon when needed to process redemptions. It's true that the loans cannot be called on demand, but extremely high rates at high utilization provide a very robust incentive for repayment or for outside liquidity to deposit. In practice these markets never display prolonged conditions of 100% utilization except in tail cases such as a market shutdown or an exploit, and DAI has generally struggled with going *above* peg, not below.

## Beyond Immediate Liquidatability

Collateral that can always be liquidated on demand without facing excess slippage or any risk of lender loss is a high bar to clear. By taking on more risk or sacrificing liquidity, enhanced returns are possible.

The basic function of a bank or banklike entity is accepting demand deposits and issuing term loans. In general, a loan is at a fixed rate, or a rate that may be updated at a fixed interval, unlike the DeFi lending markets where rates paid by borrowers are either floating market rates or adjustable by governance at need.

Historically, the vast majority of bank loans were not instantly liquidatable on demand or securitized. If a bank needed credit, they could hardly sell their assets on the market. Instead, they must borrow from another bank fixed or attract more capital by offering a higher rate on demand deposits.

MakerDAO is going in this direction with operations like the Huntington Valley Bank Deal.

Various real world asset tokenizers have created wrapped token versions of loan pools etc. Some of them have a very high cost of capital, maybe even higher than they could get off chain, while others seem mispriced relative to their risk.

Goldfinch: 17% USDC APY average + 9% token reward
Centrifuge: 3-11% DAI APY + 3.37% token reward

There are also un(der)collateralized lending platforms like Maple that lend against firms with real world balance sheets, but no direct on chain deposit of collateral in the Maple platform. This provides for example the flexibility to engage in a hedged market making strategy that is profitable for a month, too ephemeral to be onboarded as a tokenized collateral type effectively given smart contract development constraints.

Maple Orthogonal Pool: 6.7% USDC APY + 2.5% token reward

## Challenges of new backing types

These venue types represent attractive backing options for stablecoin protocols, with the constraint that there is limited secondary leverage demand, so CDP or lending pool style support is less feasible than direct PSM style acquisition. This requires a more sophisticated system than just backing a stablecoin with another stablecoin.

Too much illiquid backing, not enough surplus or reserves == bank run. We've seen it happen many times in history, but we've also seen institutions weather liquidity crises and come out unscathed through sound practices.

What's most important is to proactively maintain sufficient liquid reserves through algorithmic (or at least quickly responsive!) interest rate adjustments, and hold sufficient surplus and reserves to credibly attract liquidity to meet redemptions demand, just as Compound or Aave do with utilization-based rates.

Protocols like MakerDAO or centralized stablecoin issuers must be very cautious not to take on an excessive duration mismatch between their liabilities and assets.

Clearly enough, the longer the maturity, the more unpredictable the actual cost of capital to finance the asset to maturity will be, as there is more time for unexpected changes to occur. The largest one year increase in US treasury rates in recent history was about 8 percentage points from a trough of ~8% in summer of 1980 to a peak of ~16% in summer of `81.

In practice, unless an entity's entire book were in one year bonds purchased at the top (more likely, it would hold multiple maturities and so spread out its volatility exposure), it's highly unlikely to take anywhere near this mark to market loss on short duration (<1yr) instruments.

The instruments noted above are of course much less liquid than treasuries, and it's unlikely that liquidating them during conditions of high redemptions demand is desirable. Instead, the protocol must be able to finance its holdings and weather periods of higher redemptions demand. It's much more likely that MakerDAO can access an acceptable cost of capital and retain liquidity by raising the DAI Savings Rate than it is to have success liquidating any kind of fixed rate collateral on demand.

### When is enough enough?

There is no 100% empirical absolute mathematical answer to how much of a surplus and how large a liquid reserve a stablecoin protocol or any banklike entity requires. What can be said with certainty is that the larger the surplus, the larger portion of illiquid or higher risk backing can be tolerated. To some degree this must depend on the specific nature of the protocol's backing and current market conditions, and must therefore be adjusted from time to time using human judgement.

Volt Protocol sets a target surplus buffer of 5-20% of the circulating VOLT supply, to establish an appropriate norm of how much leverage is available to VCON holders and the amount of risk the protocol can weather.

## DeFi Devours the Repo/Secured Lending Markets

Overnight secured lending and repo market rates are both high compared to the available rates in DeFi markets. Once these collateral types can be effectively tokenized, tradfi will have access to lower cost liquidity, while DeFi will be able to greatly scale its collateral base.

The US repo market alone represents three trillion dollars in consistent borrow demand paying 3.05% at current rates, or 91.5 billion dollars in annual interest.

Is there the lending demand on chain to provide to this market at, say, 2.5% yield? I think so. Maybe we aren't ready for 3 trillion today, it can happen faster than you'd think yet always slower than speculators might hope! At this scale we can also imagine the Ethereum blockchain earning in fees quite a substantial sum relevant to its current market capitalization.

## Dollar dominance continues to increase

Not exactly a bold claim in the current environment, but it's clear that from the perspective of businesses all over the world, there is no safer currency than the US dollar and no safer and more liquid yield instrument than US treasuries. While I do expect to see some growth in Euro and other stablecoin denominations, they will not be able to challenge a strong preference for the dollar. Better settlement rails will strengthen the current dollar preference in international trade and settlement.

As a result alternative denominations are a low priority for Volt Protocol, though they are of theoretical interest and I will keep an eye out for anything to prove me wrong in adoption metrics.

### ETH is money?

The MakerDAO endgame plan misses the mark in several important ways, most notably introducing an asset-liability mismatch, contemplating a purposeful depeg, and reliance on emission of tokens with no clear utility.

One idea I do appreciate is ETHERDAI -- an ETH denominated stablecoin. This isn't the same thing as a liquid staking derivative, at least not as I consider it. It can be mintable as debt, and should be always redeemable at peg through a PSM, maintaining a certain liquid reserve. We have been considering something similar.

I expect that crypto native assets like ETH will be too volatile to compete with the US dollar for denominating business agreements for a long time to come. However, it has to start somewhere, and allowing savers to earn staking+lending yields on demand deposits of ETH is a good place to start. We will see Maple-like pools enabling market makers to take ETH-denominated loans at higher rates, and other opportunities beyond simple staking for yield.

## DeFi Certificates of Deposit

I do NOT mean this literally. What I do mean is that DeFi borrowers (or the stablecoin protocols themselves) lack access to fixed rate capital at scale. As discussed above, most tradfi loans are fixed rate, or adjustable at fixed intervals, and real world productive uses of capital commonly take time to bear fruit. If a company takes a loan to develop a new mine for copper ore, it takes time till the first revenues come in, and they would be exposed to excessive risk with an unknown cost of capital during this period.

To be able to better service real world capital demand, and more selfishly to access higher yields, stablecoin protocols need access to term deposits, not exclusively demand deposits. The surplus buffer can serve in this capacity, but equity capital is less scalable/more expensive.

For now, on chain capital is generally reluctant to commit to any kind of lockup. Risks abound and opportunities are many, users want to keep flexibility. As markets mature, I believe more capital will be comfortable accepting a 3mos-1year lockup such that early withdraw is possible with fixed fee, and fixed yield for the duration, at a premium to the yield in liquid markets like Aave or Compound. Obtaining access to fixed rate capital is a priority for Volt Protocol over the next two years and would meaningfully expand the capabilites of market governance.