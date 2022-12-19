<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>
# On the Need for More and Better Collateral
> In Which We Ponder Credit Delegation

Today I read the [FIAT II Whitepaper](https://fiatdao.notion.site/External-FIAT-II-A-Permissionless-Credit-Marketplace-523444f528a0486e9a1adbe72c584e4a). Its goals are similar to those of Volt Protocol market governance:

>FIAT II offers a market-driven alternative to existing stablecoin and lending protocols which have historically relied on manual governance for collateral onboarding. Its reduction of human intervention allows for a more scalable stablecoin supply while also opening the door for unsecured lending.

The mechanism by which this is accomplished is similar to that proposed by Joey Santoro in [Turbo](https://medium.com/fei-protocol/the-tribe-dao-strongly-believes-that-a-healthy-and-thriving-defi-ecosystem-needs-a-robust-platform-b1faea700dfa). A user provides a high quality collateral asset, against which it either mints stablecoins (FEI minting in Turbo) and deposits them in a lending pool, or grants the power to mint a stablecoin on demand to another (FIAT II).

Fiat II is better than Turbo because it goes beyond cryptoasset-only collateral.

>- **Tier I**: Lower volatility, lower counterparty risk (e.g. reserve-backed stablecoins)
>- **Tier II**: Higher volatility, lower counterparty risk (e.g. native gas tokens)
>- **Tier III**: Lower volatility, higher counterparty risk (e.g. stablecoin yield strategy vaults)
>- **Tier IV**: Higher volatility, higher counterparty risk (e.g. liquid staking derivatives)

I wonder what kind of reserve assets are likely to be used in practice, and the cost of capital to attract them vs the available yield from FIATDAO lending operations. Volt Protocol is in a similar boat where cost of capital to attract new deposits is likely to be fairly high, while boostrapping native lending markets or other yield source is nontrivial. My suspicion is that the correct tier to focus on is actually Tier III: USD-denominated yield assets. The demand for leverage against cryptoassets and their derivatives is limited, and it's challenging for an upstart to take market share. There's not enough demand to borrow against ETH etc at the rates that a younger stablecoin requires to attract deposits.

USD-denominated yield-bearing reserves such as Compound cDAI and cUSDC are a far better basis for a stablecoin or yield vault to use as reserves than ETH or raw, non-yielding stablecoins. If a protocol has a cost of capital of 5%, earning 1% instead of 0% on low risk reserves makes a big difference.

But can we do better?

## Real World Reserves

In TradFi, the reserve asset of choice is US government debt. For banks with access to the Fed discount window, credit against US Treasuries is available at essentially an unlimited depth. By extension, the open market for these instruments is also very deep. Short duration Treasuries are the ultimate preferred backing for centralized stablecoins and by extension, DAI and VOLT as well.

Getting more direct access to these instruments represents an incredibly important step forward for DeFi. There are a few paths forward on which I am seeing or hoping for progress. Treasuries are of greatest interest, but also other high quality forms of real world debt.

### Yield Pass Through

Centralized stablecoin issuers face limitations in offering yield directly to holders without onerous KYC policies. They may have found a workaround in offering yield on MakerDAO PSMs, providing yield to a DAO which can in turn pass it through in part to holders through the DAI Savings Rate. This would be far more scalable than lending against cryptoassets on Aave or Compound and represent a compelling reserve base for any younger stablecoin like FIAT or VOLT. Discussions on reactivating the DSR are [in progress](https://forum.makerdao.com/t/discussion-on-enabling-the-dsr/18759), much to my excitement.

### Tokenized ETFs

Managed instruments with rolling Treasury portfolios of certain durations. I've spoken with a team working on this, [Backed Finance](https://backed.fi), who proposed to work with MakerDAO though their product is not live yet. This sort of thing works on a similar premise to USDC, where an instrument is tokenized and mint/redeemable by KYC'd parties. Things may still be up in the air as to how this is treated legally, notably Backed Finance is a Swiss entity. Based on recent developments I suspect regulations in Europe may be more sensible than those in the US in the near term.

### Crypto Refinancing

Some projects are working on refinancing existing debt, essentially securitizing it on chain and making it more liquid than it would be in TradFi. [Agatobwe Token](https://www.agatobwe.eco) is an example of this, which I mention because Jack Chong is a neighbor in the community of minds. One good thing about this sort of product is the reduced managerial cost compared to a tokenized ETF, and its "self liquidating" character in that the bonds must be bought up from the market by the issuer. The specific issuance is still fairly niche. Coinbase corporate bonds with 2028 maturity are yielding over 16%, which I would love to be able to get access to on chain. Potential total secondary market liquidity is key, and the market will converge on the most liquid assets as preferred.

It's possible that composite instruments are the solution, ie a bundle of individual loans like the current Agatobwe token. This is in a way how we got the 2008 financial crisis with bundled mortgage loans, but the devil is in the details and just because something is a touch more complicated, does not make it evil. We'll be paying close attention to those details as this niche of the industry develops.

### On Chain Origination

A more distant fruit to pluck but of great interest. Consider the idea of a bank issuing bonds on chain that are traded nowhere else, preferring Ethereum as its only means of settlement. Tokenization can meaningfully reduce the cost of security issuance and lower cost of capital for various businesses around the world. Issuance of high quality corporate debt on chain is a major step towards Ethereum as world economic nexus and heir to the US-centric banking system.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>