<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>
# Redundancy Does Not Solve the Oracle Problem

Many readers will be familiar with the challenge known as the oracle problem, that is, how can a smart contract know certain things like the price of ETH which are not natively available in the on chain state, the way a user's balance would be?

The DeFi lending ecosystem today relies on trusted oracles, mostly Chainlink, while MakerDAO uses an in-house system. These oracles have two failure modes: manipulation of the underlying markets they are observing (Chainlink oracles aggregate prices from multiple centralized and decentralized exchanges, but for an illiquid token, the whole market could be manipulable), and false data reporting by the oracle if it has been compromised.

The major alternative to trusted oracles that has been used in production is the Time Weighted Average Price (TWAP) oracle from Uniswap or other decentralized exchange. These oracles have a defined cost of manipulation, which will be prohibitively high so long as there is a sufficient amount of liquidity in the market and an appropriate duration used.

Some have suggested that oracles need to be overcollateralized such that the cost to manipulate the network exceeds the value secured. The issue with this notion is that there is no way to programatically detect and slash a malicious oracle that could not itself be manipulated. Even if it were possible to reliably slash a malicious oracle, this approach would suffer from severe scaling constraints.

Another naive solution to oracle risk is to add a backup oracle. This is what was done in [Compound v2](https://docs.compound.finance/v2/prices/) and [Liquity](https://www.liquity.org/blog/price-oracles-in-liquity) among others. Both use Chainlink as a primary oracle while relying on either a Uniswap (in the case of Compound) or Tellor in the case of Liquity.

The question then becomes, how do you know when to switch to the backup oracle? Unfortunately, it's the oracle problem all the way down.

>The Compound Protocol uses a View contract (“Price Feed”) which verifies that reported prices fall within an acceptable bound of the time-weighted average price of the token/ETH pair on Uniswap v2, a sanity check referred to as the Anchor price.

>Additionally, when Liquity is using the primary Chainlink oracle, it checks the Chainlink price deviation between two price updates. If the difference is greater than 50%, and the Tellor price doesn’t match the new price, Liquity considers the primary price incorrect and switches to using Tellor. If the Tellor price does match, Liquity infers that the major price change is a legitimate market movement, and continues using Chainlink.

[Gryroscope](https://docs.gyro.finance/gyroscope-protocol/oracles/consolidated-price-feed) has a more elaborate version of the same idea.

>The Consolidated Price Feed consolidates data from four different types of sources which have varying trust assumptions:
Chainlink. The security model of Chainlink amounts to effectively a large but trusted multisig.
AMM TWAPs. These TWAPs do not require trust, as they exist on-chain and do not require a relay. However, they are manipulable and slow tracking estimates of price.
Exchange-signed prices. Since the signatures for these prices can be verified on-chain, the relay for these prices does not need to be trusted, though the data provider (i.e., the exchange) is a trusted counterparty.
Observing changes to protocol state. The information about how agents interact with the protocol is observable completely on-chain with no trust assumptions. Unusual behavior can be used to flag suspicious settings when oracle prices may be wrong.

The issue is that this mechanism is only helpful if the cause of the primary oracle's failure is benign. If not (whether the Chainlink oracle itself is malicious, or if the underlying markets are being manipulated), including a switch to a backup oracle can lower the costs of an attack.

Consider a protocol with two oracles, A and B, where A has an attack cost of 1 ETH/ block and B has an attack cost of 0.1 ETH per block, and A is used as the primary oracle. If only A were used, the cost to attack the protocol would be 1 ETH per block. On the other hand, if the protocol switches to use oracle B when there is an unusual deviation in A, an attacker could first manipulate A, then manipulate B at a lower cost.

Therefore, we can't be sure whether it's better or worse to have a backup oracle -- it depends on whether you're more worried about Chainlink downtime or a purposeful attack. The idea that by aggregating and cross referencing enough oracles we can resist manipulation is a dead end. There is an unavoidable tradeoff between being responsive enough to current price movements, and current market pricing being manipulable, if we remain bound to using trusted price sources. We must look elsewhere to acheive a truly censorship resistant lending market.

How do we move beyond trusted price sources? For starters, let's recognize that for peer to peer lending, we already do not require trusted oracles. While this sort of lending doesn't have much traction, Ruler loans did have a peak TVL over 100m. The issue is that most individuals who might hold DAI or deposit on Compound neither have the sophistication nor the resources to manage a loan book. Setting loan terms (collateralization requirements, interest rate, maturity) such that they are +EV for the lender is not simple, and this type of lending is more costly in gas than lending pool models that use trusted oracles.

Is it possible to make a lending pool (where the setting of loan terms is done by either algorithm or a smaller subset of users) without introducing a trusted oracle? I think so, and that the key lies in the following ideas:
- the only sure way to measure a price is to buy or sell
- while "totally trustlessness" and "pool" are a contradiction in terms, with checks and balances we can make a system that works so long as there is an **honest minority**

When there is a dispute about a price, an auction is the only way to settle it. As long as the process for triggering an auction has a cost to prevent griefing, and this cost is repaid if the auction's clearing price reveals the "liquidation" was justified, it's possible for an honest minority among a system's users to prevent malfeasance among its governors.

The above doesn't mean mainstream oracle providers are useless; but it means that existing governance systems have no clear way to reach a safe final resolution when there is a malicious oracle that should be disputed. A related idea is decoupling the pricing of the asset when used as collateral, and the mechanism for triggering liquidations. For example, a lending market might price an asset ExampleCoin no higher than whichever is lower of the Chainlink price and a Uniswap TWAP when lending against it; but price it no lower than whichever is higher of the same when lending out ExampleCoin against other collateral assets, and separately have a permissionless system to trigger liquidation auctions outside the oracle feeds.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>