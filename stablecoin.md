# Are stablecoins money?
> the rise of digital banknotes

Lately I've been learning and writing about the [important differences](semantics.md) between money, credit, and money-substitutes.

What is a stablecoin and where does it fall in these categories? Is DAI money?

The [original MakerDAO whitepaper](https://makerdao.com/en/whitepaper/sai/#overview-of-the-dai-stablecoin-system) defines DAI as a "collateral-backed cryptocurrency whose value is stable relative to the US Dollar". 

The (remarkably terse) [Wikipedia article](https://en.wikipedia.org/wiki/Stablecoin) defines a stablecoin as:

>Stablecoins are cryptocurrencies where the price is designed to be pegged to a reference asset. The reference asset may be fiat money, exchange-traded commodities (such as precious metals or industrial metals), or a cryptocurrency.

Compare this to a closely related concept, [the banknote](https://en.wikipedia.org/wiki/Banknote):

>A banknote—also called a bill (North American English), paper money, or simply a note—is a type of negotiable promissory note, made by a bank or other licensed authority, payable to the bearer on demand. Banknotes were originally issued by commercial banks, which were legally required to redeem the notes for legal tender (usually gold or silver coin) when presented to the chief cashier of the originating bank. These commercial banknotes only traded at face value in the market served by the issuing bank. Commercial banknotes have primarily been replaced by national banknotes issued by central banks or monetary authorities.

In other words, a stablecoin is no different from a banknote, **a cryptocurrency redeemable by the bearer on demand for hard money (usually US dollars) at a fixed price**. The precise mechanism by which this is accomplished and its limitations may vary, but the expectations of the users and the consequences of failing to support reliable redemptions at peg are clear. Reliable redemptions at peg ≠ unlimited on demand redemption, stablecoins evidently hold peg despite peg mechanisms with varied latency. What's important is that a closed arbitrage loop is consistently available on a reasonable timespan and fee.

The creation of banknotes predates any modern legal framework. It's no surprise that they would appear and proliferate in the digital environment where there is no centralized state issuer.

![By John E. Sandrock - Ancient Chinese Cash Notes - The World&#039;s First Paper Money - Part 1 (The Currency Collector)., Public Domain, https://commons.wikimedia.org/w/index.php?curid=72426460](Hue-tzu_(Song_Dynasty_government_issue),_1023_-_John_E._Sandrock.jpeg)
>By John E. Sandrock - Ancient Chinese Cash Notes - The World&#039;s First Paper Money - Part 1 (The Currency Collector)., Public Domain, https://commons.wikimedia.org/w/index.php?curid=72426460

## Are banknotes money?

No. Banknotes are money-substitutes that may trade at a discount to the base money or to each other, or at a premium if the issuer seeks to buy them back. Stablecoins are the same. If something goes wrong (or is perceived to have gone wrong) with a stablecoin issuer, it's possible for it to trade below peg until redemptions can occur. In the case of DAI, it routinely spent months above $1 when holder demand exceeded demand to mint prior to the introduction of the PSM. sUSD is a similar example today, trading at $1.02.

The closer it is to real money (the more readily convertible), the better a money substitute is. A stablecoin should be 1:1 redeemable at peg with as little latency as possible. Any volatility degrades the user experience. This is one of the reasons why DAI, with a 1:1 free conversion to USDC (which in turn has a 1:1 free conversion to USD, though not necessarily as fast as a single block), is the dominant decentralized stablecoin. 

## What are banknotes good for?

Banknotes do **not** need to be generally accepted exchange media to be useful. To sketch a simple example, merchants could make use of them for bulk settlement, as it is inconvenient to store, move, and exchange large amounts of physical coins or quantities of metal. A few large merchants might mutually agree to accept each others' promissory notes, and only occasionally settle in physical coins to reduce their costs. These notes might come to be accepted by anyone well familiar with these businesses in a certain area, who can conveniently redeem them when they wish to.

The key reason to use a non-yield bearing banknote, then, is for convenience, avoiding the alternative of transacting using the less portable base money. This analogizes very well to US dollar stablecoins, which cannot natively be transacted in real time or across borders without incurring significant risk and cost. This is a natural property of cryptocurrencies like Bitcoin or Ethereum. Exchanges that already do significant trading volume between fiat currencies and cryptocurrency are natural issuers of stablecoins.

## How are banknotes backed?

The idea of a banknote is: you give the bank gold coins, the bank gives you a paper note. When you or anyone else returns this note to the bank, the bank pays out gold coins. There may be restrictions on the minimum size to mint or redeem directly, or on the number of parties who can transact directly with the bank. The same is true of a stablecoin like Tether.

The bank does not keep all of the gold face value of the banknote on hand. Instead, it makes loans. While the bank commits to buying and selling banknotes on demand at a fixed price in gold coins (though perhaps not in unlimited quantities, and not without fee), what actually backs the banknotes is the credit of the bank. Actual gold reserves will inevitably be only a small part of the bank's assets -- as little as possible, as they are costly to store and produce no revenue.

Banknotes are credit instruments, regardless of their denomination, representing a claim on the bank's assets. If the bank cannot redeem its notes, it is insolvent. Just like banknotes, [stablecoins are credit](https://cryptobanking.network/stablecoins-currency-or-credit/).

## Limits on banknote issuance

It's phyiscally possible for a bank to issue banknotes whose face value exceeds its assets. However, this will cause the market to react by devaluing that bank's notes, and in the banks creditors seeking their due. If a bank or stablecoin issuer's liabilities exceed its liquid assets, it's possible to survive insolvency through equity dilution. Even if the face value of liabilities exceeds those of liquid salable assets, there may be other assets that justify the value of the equity in a sale. This applies in the real world, as in the case of Credit Suisse where depositors need not fear any losses [even as the CEO departs and outside capital is required](https://www.reuters.com/business/finance/credit-suisse-approached-middle-eastern-fund-capital-injection-source-2022-10-17/).

We can also consider an actual DeFi case study of InverseDAO and associated stablecoin DOLA.

InverseDAO took on bad debt in a few incidents, including an oracle manipulation on INV that led to [over 15m in bad debt](https://twitter.com/InverseFinance/status/1510282040809299972?s=20&t=NTNUj9UAashwjfIfL5I-4g). The team is working toward repayment, but one must wonder, if DOLA is meaningfully undercollateralized, why is it still trading at only 13 bips off peg?

The answer lies in the fact that InverseDAO is obtaining sufficient credit elsewhere to backstop the peg of DOLA. They've done this by heavily incentivizing Curve pools, such as the main DOLA-3CRV pool with over half the DOLA supply. Thanks to the high yields available, the DOLA supply floor was about 24m, well above the gap in the balance sheet which is ~15m.

Banknotes work the same way -- as long as someone will accept a newly issued note at par, the bank can go on issuing, but eventually this information will propoagate into the market and increase the bank's cost of capital or lead to a run. The bank is **drawing on a limited reserve of credit**, not creating money out of 'thin air'. The fact that we cannot precisely measure the amount of credit available to a bank does not change this fact.

## Why does this matter?

I have been tediously insisting that the following distinctions are important and [non-semantic](semantics.md):

1) stablecoins and banknotes are money substitutes, not money
2) banks cannot create money, both printing of banknotes and giving of loans are drawing upon available credit, not creating new money

This matters from a regulatory standpoint, and is useful when thinking about design. Whether a bank or stablecoin issuer can create money (and thus cause inflation) is a politically significant question. The fact that they *cannot* is an important justification for relaxed regulation and allowing a new free banking era to blossom.

As we realize that a stablecoin issuer or a bank has a limited amount of credit that it can draw upon, we begin to ask, how much credit does it have? Rather than an arbitrary power of money creation checked by law, we are looking at a limited well of credit supplied from the outside. How can this be measured, why and how does it change? What are the terms under which we receive and give credit? Can they be altered in any beneficial ways?

## The need for term deposits in DeFi

Seb Ventures has conducted [maturity analysis on DAI](https://forum.makerdao.com/t/modeling-dai-maturity/15961). I'm sure Circle has similar data on USDC -- if only I could see it! Ensuring that the backing matches the maturity profile of DAI as closely as possible will be essential to ensure peg stability while maximizing yield on the backing.

No matter how much we analyze and try to predict, the fact remains that a demand deposit is a demand deposit. It would strongly benefit stablecoin issuers to be able to borrow for fixed terms and effectively bound their maximum redemption demand in a given period. Likewise, there are surely users who have funds they know they will not need to access for X months and interested in a yield premium.

Why hasn't fixed rate lending taken off so far? Purely on chain lending (overcollateralized cryptoasset collateral) isn't even enough demand to back DAI alone, let alone to support a liquid rates derivatives ecosystem ie of users wanting to long and short the rates on Aave or Compound. There simply aren't enough people who want to borrow at fixed rates against cryptoassets, or go long/short yields on existing platforms.

On the other hand, there is real demand for yield. If MakerDAO were to a DAI Savings Rate of 1%, this would set a floor on stablecoin supply rates across DeFi and cause their TVL to balloon. I'm equally confident that if MakerDAO offered 3%+ for "yield locked DAI" on a 6mo term, users would come.

It's unlikely many would trust a newer, smaller stablecoin issuer enough to lock up their capital. A system to exit early with reasonable fee might mitigate this, while still providing a hedge to the protocol in a liquidity crisis. It's clear that this should be internal to the protocol, forcing users to access a secondary market with unpredictable pricing, MEV, etc is undesirable.

## Maturity Over Time // Trust Premium

It takes time to build credit. The largest banks mostly originated in the 1800s or earlier (though some have shed their skins through multiple layers of mergers). While the mania of DeFi summer saw very high deposits in recently deployed protocols, this was invariably short-lived. Exchange stablecoins like BUSD and GUSD have demand profiles highly correlated with demand to trade on these exchanges, and a demand base if they choose, as Binance has, not to hold rival stablecoins in excess of the amount needed to process redemptions.

DAI is alone among decentralized stablecoins in maintaining a stable base of EoA holders. A subset of this stable base could safely be deployed into longer maturity backing (>1yr maturity). Any meaningful DAI savings rate would attract substantial deposits. Other stablecoins like FRAX or LUSD require significant liquidity incentives and have a cost of capital higher than their sustainable revenues. The stable base of DAI demand also provides stability to the MKR price, reflexively. As mentioned above, even with negative book value when considering only financial assets and liabilities, there are additional equity components for both Credit Suisse and Maker that allow them to escape insolvency through equity sale at need.

## An Ounce of Prevention // A Pound of Cure

Equity dilution to prevent insolvency, or even bailout when the "book value" is negative, are amazing from the perspective of depositors who are protected from losing value. However, they are obviously undesirable for the shareholders of the bank or the MKR holders. It's much better to raise sufficient equity capital when times are good to weather any losses or liquidity crunches.

Credit Suisse has had many better opportunities than now to raise additional capital at lower rates and cost. Likewise, MakerDAO has many better opportunities than during a [Debt Auction](https://docs.makerdao.com/keepers/the-auctions-of-the-maker-protocol) to sell MKR for DAI and grow its surplus.

I have to shake my head at the fact that expanding the surplus buffer through MKR auctions isn't part of [the Endgame Plan](lettertomaker.md).  Luca Prosperi wrote [in Dirt Roads 37](https://dirtroads.substack.com/p/-37-capital-structures-for-stablecoin?r=k87cd&s=w&utm_campaign=post&utm_medium=web), and together with [Hexonaut](https://twitter.com/hexonaut) [in a forum proposal](https://forum.makerdao.com/t/aggressive-growth-strategy/13958/1), in favor of a largely expanded surplus. Instead, the going plan is to [use what little there is to buy ETH](https://forum.makerdao.com/t/mip84-activate-protocol-owned-vault-emulation/17713/71), and to use MKR tokens for an emissions scheme. It is what it is.

Volt Protocol will maintain a surplus buffer or insurance fund target of 5-20% of the outstanding VOLT supply. Below the target, auctions of the VCON governance token will recapitalize. Above it, VCON holders will be able to redeem for their pro rata share of the surplus.