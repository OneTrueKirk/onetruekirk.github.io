# Governance Roundup Nov 14

This post is the first in a series of public checkpoints of governance activity in all protocols where Volt Protocol has made PCV deposits.

## Compound v2

Reduce xSUSHI Collateral Factor 73->70%. Proposed by Gauntlet. [Executed November 6](https://compound.finance/governance/proposals/133). No objections here -- I'd prefer to see supply paused for SUSHI and the market gradually deprecated. It's small as is and induces needless risk to the protocol.

As the basis of many integrated protocols, we'd like to see Compound v2 hardened to the maximum possible extent, though it would be great to see the addition of some major neglected asset categories like stETH and rETH. 

Otherwise, all quiet on the governance front with the other dramatic events of the week.

## Morpho

Morpho DAO [votes to add delegation feature for governance](https://vote.morpho.xyz/#/proposal/bafkreigzfyi7m3he4xvg7fj3zs2r6apt2hgofyi4x2uv3ptfjb23hen7uu). If interested you can [delegate MORPHO voting power to me](morpho_delegate.md). No one has yet done so at time of writing, maybe you will be the first.

There is a discussion about adding FRAX as a borrow asset to Morpho-Aave; I [commented in support](https://forum.morpho.xyz/t/mip-listing-frax-on-morpho-aavev2/166/5?u=onetruekirk) even though this isn't directly relevant to Volt Protocol which only deposits in Morpho Compound. While I'd like to be able to use Aave, it is a worse offender than Compound for long tail assets. Maybe this can change in the future.

## MakerDAO

There's an active discussion about enabling the DAI Savings Rate, I [chimed in to speak in favor](https://forum.makerdao.com/t/discussion-on-enabling-the-dsr/18759/18?u=onetruekirk). Would be great for us at lower risk than Compound if it offers a similar yield.

Quite a few governance polls submitted today, most without votes yet.

A few related to real world assets:

* [CoinShares](https://forum.makerdao.com/t/mip86-coinshares-active-treasury-management/17900) government and corporate bonds, 100-500m allocation. I owe more time to looking at the specific bond composition, but with the short term focus of less than a year and reputable custodian, this makes sense to pursue.
* Monetalis proposes to invest in [Arrow lending operations](https://forum.makerdao.com/t/mip89-monetalis-arrow-andalusian/18338). Despite the ESG label, it looks like mostly fairly boring securitized real estate.
>Examples of collateral would include:
>Granular UK residential development and completed homes
>Irish energy efficient homes (refurbished from old, inefficient housing stock)
>Dutch green office buildings and facilities
>Large scale solar installations
>Social housing projects across UK and Europe
>EV charging stations and battery storage
>Electric vehicle purchasing contracts
* Also Monetalis, proposing to invest in [mortgage backed securities](https://forum.makerdao.com/t/mip88-monetalis-redwood-friesian/18336) in the US. Personally, I'd rather see a much greater focus only on Treasuries, and see no reason to risk most other things until that is well developed, but this is a very conventional and liquid asset class for banks and banklikes.

I mostly like these -- better than the status quo of trust only in Circle with no yield, if not perfect. Would like to see a more credibly neutral org taking the lead than Monetalis, but it is what it is.

One that stood out: [OUSD](https://forum.makerdao.com/t/mip87-ousd-decentralized-rewards/18216) proposes to allocate 100m to the OUSD stablecoin. A bad proposal which I'm sure will not be favored. The last thing MakerDAO needs is to deposit in venues smaller, less secure, and less liquid than itself. On the other hand, DAI makes a great backing for smaller stablecoins like OUSD and VOLT. "Nothing personal kid".

Of greatest significance is the vote to [prevent the use of the surplus buffer to buy ETH in the "protocol owned vault"](https://forum.makerdao.com/t/mip84c10-sp1-modify-emulated-surplus-buffer-upper-limit/18315?) As we've previously [argued](lettertomaker.md), disposing of the protocol's USD denominated surplus buffer to buy ETH and worse, taking leverage on that position is a foolish and shortsighted notion. To quote [Luca Prosperi](https://dirtroads.substack.com/p/47-tribes-and-endgames-daos-stretching),
>Conceptually, the Surplus Buffer would go from being a cash-like cushion to protect against unexpected losses (in line with the concept of Common Equity Tier 1 capital of traditional banks—we had discussed it already here) to some sort of DAO-owned hedge fund with yield and volatility.

If you've got MKR or delegations, please vote YES! to modify the surplus buffer upper limit (the threshold above which any excess can be used to buy ETH, this proposal sets the threshold to 1 billion, essentially enforcing accumulation of DAI in the surplus).
