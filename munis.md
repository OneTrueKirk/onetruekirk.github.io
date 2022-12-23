<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>

# Onchain Markets for Municipal Bonds
> to boldy go where no exchange has gone before

Municipal bonds or munis, issued by states, counties, or cities, are ripe for tokenization. The roughly $4 trillion municipal bonds market is illiquid and fragmented among numerous dealers without open orderbooks[^1]. Lower liquidity and high spreads are invariably priced into the bond yields[^2] and thus the cost of capital for the issuer.

While not all jurisdictions are trustworthy counterparties, many are, and their cost of capital might be reduced by the transparent 24/7 markets which Ethereum provides.

# Why DeFi

I may be preaching to the choir here, but let us review the staggering difference between opaque dealer markets and the DeFi markets we know and love. On Uniswap, everyone in the world has access to the same price information in the public "orderbook" of Uniswap v3. In a dealer market, the "LPs" keep their prices to themselves to a large extent, meaning prospective traders struggle to acheive quality and rapid execution for their trades. Like all TradFi assets, munis can be bought or sold only in certain trading hours, and have limited venues where they are accepted as collateral.

While I'm [critical of AMMs](liquidityauction.md), they make it much easier for buyers or sellers to decide how to price their orders compared to an opaque dealer market. In this regard, as well as their 24/7 global accessibility, they are a far superior trading venue to a tradfi dealer market. My critique is that they are suboptimal from the perspective of a liquidity provider, not from that of a trader.

It's more challenging to think about incorporating these assets into today's collateralized lending models as on Compound or Aave. MakerDAO's real world assets are not regularly marked to market and under a strict liquidations contol. The [callable loans](pcl.md) model I've been working on is an effort to solve this problem. The gist of the idea is that if it's not possible to get a trustworthy oracle for an asset that both lender and borrower can agree is credibly neutral, the alternative is to make loans callable at a defined price and using an auction mechanism to ensure a fair execution.

With the existing AMMs as a crude orderbook and a callable loan system, we can envision a far more credibly neutral and efficient financial infrastructure for municipal debt or similar assets. Note that even this infrastructure can't remove the risk of insider information asymmetries. The inherently public nature of the relevant information is one reason I feel municipal debt is well suited for tokenization. Compared to lending to a private firm, it's much less risky insiders will be able to successfully conceal information for long to their own advantage, especially as various records must be made available to the public upon request.

# The Devil is in the Details

As always, real world asset questions come down to how trustworthy the custodian is and the legal framework under which the assets are custodied, tokenized, and redeemed for the underlying.

In the case of munis, it would be ideal for the issuer themselves to approve of the tokenization. We can hope that one of the jurisdictions seeking to differentiate itself with innovative legal frameworks might attempt such a thing. If the Société Générale can make deals with MakerDAO, it doesn't seem strange that Wyoming could tokenize its debt in pursuit of modestly lower rates.

Legal infrastructure is outside my wheelhouse, but as we are keen to intregrate high quality real world asset collateral into Volt Protocol, I am avidly researching this topic and following efforts in the area closely. If you're working on tokenizing things like government bonds in any jurisdiction, please do get in touch.

I'm hardly the first to suggest this (see Consensys [up to the same thing in 2020](https://www.ledgerinsights.com/municipal-bonds-blockchain-tokenization-consensys-broker-acquisition/)), but there is as yet no one tokenizing these assets on public ledgers. This is probably because municipal bonds are securities. Is it legal for a government entity to tokenize its securities and issue them on a decentralized exchange? I'd love to see that one put to the test. 


The writers of the Securities Act of 1933[^3] made it clear enough what their goals were:

```
To provide full and fair disclosure of the character of securities sold in interstate and foreign commerce and through the mails, and to prevent frauds in the sale thereof, and for other purposes.
```

This is not intended to prevent government-issued securities from being freely exchanged on a public ledger! Quite the opposite, and I suspect the authors of this act would recognize the Ethereum network and the neutral markets it supports for the technological marvels that they are.

[^1]: The paper which inspired me to think that munis could benefit from DeFi tokenization by Green, Hollifield, and Schurnoff can be [found here](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=668847).

[^2]: I'm currently working my way through [Market Liquidity](https://thierryfoucault.com/book-new/) by Foucault et al which I recommend on this topic.

[^3]: The full text [available here](https://fraser.stlouisfed.org/title/securities-act-1933-5878) courtesy of the St Louis Fed.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>