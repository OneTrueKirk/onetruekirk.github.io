# wBTC is Dead, Long Live Wrapped Bitcoin

Wrapped Bitcoin (wBTC) has long been a sleepy giant of Ethereum DeFi. It has the fifth largest value of any asset on the Ethereum network (after ETH, USDT, USDC, and Lido stETH), occupies spot number 15 on the Coingecko rankings. Like USD stablecoins, it experienced a substantial supply drawdown from its 2022 peak. Unlike them, it has been flat since the drop finished instead of making a U shaped recovery. It has a meagre ~$2m in annualized revenue against $8.85b in total value locked. This perhaps explains the recent scandalous news -- BitGo, the wBTC custodian, is partnering with Justin Sun-affiliated BiT Global (nominative determinism?), in order to "diversify custody operations and cold storage across multiple jurisdictions".

In response, premier DeFi platforms like MakerDAO have [taken steps](https://forum.makerdao.com/t/wbtc-changes-and-risk-mitigation-10-august-2024/24844) to offboard wBTC, rival protocols like tBTC have made a bid for integrations, and Coinbase has launched cbBTC, the heir presumptive to the wBTC throne.

A few questions need to be asked:

1. What is His Excellency's motive for taking a stake in wBTC?
2. How is cbBTC different from wBTC?
3. What are the similarities and differences between wrapped Bitcoin and centralized USD stablecoins?
4. How does tBTC work, and is it really possible to make a decentralized wrapped asset?

## An Excellent Question

To quote Monet Supply's excellent post in the Maker forum,

```
This bears some similarity to the previous situation concerning control of the TUSD stablecoin, which was discussed in the Maker forum here. Since TUSD was placed into Justin Sun’s control, it has seen market deterioration in operational processes and transparency, including the resignation of the previous management team, suspension of real time proof of reserves, and several significant depegs caused by interruptions in redemption service. We have also seen other Sun affiliated projects show worrying signs of possible misappropriation, such as the substitution of Huobi’s USDT reserves with stUSDT, a Sun controlled RWA project that purports to hold a reserve of US treasury bills but has not provided clear audits or evidence that the backing exists. On the whole, we find that Sun’s involvement as a controlling interest in the new WBTC joint venture presents an unacceptable level of risk.

We also note that Bitgo itself seems to have had some negative developments recently, including a failed acquisition by Galaxy Digital where Galaxy backed out for undisclosed reasons. This, along with the unexpected decision to divest from the WBTC product, may be indications of financial distress within Bitgo, and reflects negatively on Bitgo’s counterparty risk. While some of the risk factors are somewhat speculative, it makes sense to err on the side of caution given the critical role WBTC collateral plays within defi.
```

The deal between Bitgo and BiT Global will not *immediately* result in Justin Sun having access to the Bitcoin underlying wBTC, and it would be difficult for Sun to directly abscond with BTC that has proof of reserves applied to it. Even so, his motives for this deal are worthy of scrutiny. wBTC's revenue is too low to be a motivating factor, leaving us with two general options:

1. Buying legitimacy and TVL

It's possible that His Excellency wishes to drive further BTC usage on Tron, thus boosting TVL and transaction fee revenue. Bringing in a reputable outside custodian could likely be beneficial for this goal.

2. Boiling the frog

While this "partnership" does not materially change the legal status of wBTC initially, His Excellency could always do so later, allowing a period of safety after the acquisition before modifying the custody rules to allow activities like rehypothecating the wBTC backing. While obviously questionable, it's also likely that this could be done 'legally' and allow Mr Sun to derive greater revenues from wBTC without such a drastic action as stealing the underlying. 

## The Heir Presumptive

cbBTC, Coinbase's answer to wrapped Bitcoin, is fundamentally a similar asset, with the important difference being that it possesses a *freeze function* like USDC or USDT to seize cbBTC which is held by sanctioned or known criminal addresses. I'm not a fan of this, but on a personal level I would much rather trust Coinbase with my assets than Mr Sun, and plan to shortly convert my wBTC into cbBTC. This new asset is harmonious with Coinbase's push toward greater onchain operations. Users will be able to seamlessly move BTC onto Base, and liquidators or arbitrageurs will be able to take easy advantage of Coinbase liquidity.

Relatively speaking, it will be easier for cbBTC to outcompete wBTC than it was for USDC to challenge USDT, since a much larger portion of it is used by technically savvy users in DeFi and it depends much less on real world integrations for its primary use case. For example, more than 20% of the wBTC supply is on Aave, while only around 1% of the USDT supply can be found there.

wBTC will likely remained preferred by users in Asia due to its well established liquidity, the new Hong Kong based custodian, and the lack of a freeze function, so I believe it will retain dominance over cbBTC for the near future. Perhaps the market will reach an equilibrium in which cbBTC takes 30-40% of the wrapped Bitcoin market over the next few years.

## A Stablecoin without a Margin

Wrapped Bitcoin (whether wBTC or cbBTC) is basically the same thing as a US dollar stablecoin, with the key difference being that there is **no naturally yield bearing form of Bitcoin**, and therefore **no margin for the issuer**. Stablecoin issuers like Tether can make very healthy profits investing in short term treasuries (currently, the highest profit per employee of any company in the world), while Bitcoin custodians have no similar opportunity without engaging in higher risk strategies like lending BTC to margin traders (which, for good reasons, none of them engage in presently).

Coinbase is in a good position as an issuer because they must *already* have all the infrastructure needed for BTC custody and processing deposits/withdrawals for their exchange business, so issuing a tokenized form, while not adding much revenue, also does not add much to their costs. While Coinbase will likely earn less from use of cbBTC on Base than they would from swaps native to the exchange, these additional products also help them compete for users with their rival exchanges and draw more arbitrage flow, offering a holistic benefit to their business.

## tBTC -- Too Good to be True?

What about "decentralized" alternatives like tBTC?

First of all, tBTC currently has a permissioned set of minters and guardians who can veto mints, so it is best considered in the same category as cbBTC or wBTC.

In terms of roadmap toward permissionlessness, much like oracles, the general problem with this class of applications is that the revenue they can extract is low compared to the TVL they secure, and thus there is a high risk of attack if they have open validator sets and grow to a large size.

In the case of Threshold, tBTC has a total value locked of over $200 million, while the T token's fully diluted valuation is $237 million. If Threshold signers were selected randomly in a truly permissionless way, even if an attacker only held ~10% of the staked T, it would be only a matter of time before they were selected to form a committee all by themselves. Taking wBTC as an example, Threshold's revenues cannot be expected to be large enough to maintain economic security.

I've had some discussions about whether restaking can be productively applied to a Bitcoin bridge. For now I am skeptical. The margins, as noted above, are quite small to induce users to put their capital at risk, and it's not clear that there is any trustless way to enforce slashing conditions.

## Conclusion

Ethereum is the cheapest place available to take loans against your (wrapped) BTC, so I anticipate net growth in the BTC-on-Ethereum market over the next years. Coinbase cbBTC will take some market share from wBTC, but probably not flip it in the near future. Bridged assets **require** trust assumptions, since economic security is necessarily limited and slashing cannot be made trustless, so for now I think it is best to pick the most reputable custodian, and will personally be using cbBTC going forward.