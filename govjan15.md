<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>
# Governance Roundup January 15 2023

This post is the third in a series of public checkpoints of governance activity in all protocols where Volt Protocol has made PCV deposits.

Read past issues here:
* [November 14](gov14nov.md)

* [December 5](govdec5.md)

![img](nasturtium.jpg)
> when it rains, it pours

## Compound v2

Upcoming/Under Discussion:
* [Upgrade Compound II's Oracle to UAV3](https://www.comp.xyz/t/upgrade-compound-ii-s-oracle-to-uav3/3826). While at 

Recent:
* Jan 2 : "[Risk Parameter Updates for 5 Collateral Assets](https://compound.finance/governance/proposals/141)". Decreases the collateral factor on BAT, COMP, and SUSHI by 3% each. The community signalled via Snapshot back in September that collateral factors should be reduced by a [maximum of 5% per proposal](https://snapshot.org/#/comp-vote.eth/proposal/bafkreiar7qfbmmabclsogilncy542cyenehjulmdhhewuzojdooer4tnje). I think this shows poor judgement on the part of Compound stakeholders and am in favor of a more rapid offboarding of potentially toxic collateral, especially BAT and SUSHI. It also raises the borrow caps of LINK and UNI, a proposal which I support -- making these assets borrowable at larger scale does not pose additional risk to stablecoin lenders and could increase utility and revenue in the protocol.
* December 16 : "[OpenZeppelin Security Partnership - 2023 Q1 Compensation](https://compound.finance/governance/proposals/139)". This is a lot of money, and it feels like Compound might be better served by a few full time security engineers at Compound Labs.
* December 15 : "[Reserve Maintenence](https://compound.finance/governance/proposals/138)". Housekeeping, not particularly relevant to us.

## Morpho

* Jan 12 : "[Governance and Snapshot Update](http://vote.morpho.xyz/#/proposal/0xf34f13a4cb01bfbe5be17236520bbfbf53d76367949cdcf33a3c23083f1267d1)". Happy to see Morpho implementing timelock delays on governance. The changes will be audited and not going live immediately.
* December 29: "[FEI Market Deprecation](https://snapshot.org/#/morpho.eth/proposal/0xf1c28824385f5c66cf514ba37f1717b0ecd1608ddf3730f7deacc5d4d26f072c)". *salute*
* December 27: "[Age 3 - Epoch 1](http://vote.morpho.xyz/#/proposal/0xf402161143c42ac5edf6589b7833eb760cbe556e18451a232e6be3d34d06f287)". Seems like Morpho users like Aave more than Compound. Relatively more rewards will be going to the Aave market. On that note, Volt Protocol expects to integrate Morpho-Aave alongside our market governance launch.

## MakerDAO

As always, a lot going on.

* January 9 : "[MIP63 Maker Keeper Network Amendment (MIP4c2-SP31)](https://vote.makerdao.com/polling/QmRswbkm). Maker working on improving its keeper system including redundancies.
* January 9 : "[MIP55c3-SP14 Defense Fund](https://vote.makerdao.com/polling/QmUbqKMy). Establishing a $5m legal defense fund for active DAO contributors. Hopefully it doesn't need to be used too quickly!
* January 9 : "[MIP92 Onboard PSM USDC to Yearn to earn Yield](https://vote.makerdao.com/polling/Qma4jEPY)". I spoke out against this one in the thread and will reiterate those concerns here. The strategies available to the Yearn vault are too risky and offer too little yield to justify this risk to be included in the DAI backing. Not all that long ago, I made a fool of myself by arguing in favor of MakerDAO adding FEI as collateral. Now, I've come around to the view that only assets *more liquid than DAI* should be onboarded as collateral. Anything else represents unnecessary risk for the DAI holders. With three month Treasury bill yields at 4.5%, it's hard to justify deployments into smaller DeFi lending markets with governance risk (remember when Compound [accidentally froze the cETH market](https://thedefiant.io/compound-ceth-frozen?) at less than 2% yield. Nothing against Yearn, depositing funds into any other DeFi lending market whether Aave, Compound, or Euler, isn't the right approach for Maker to manage risk.
* January 9 : "[Commercial Risk and Legal Domain Work to Support...RWAs](https://forum.makerdao.com/t/mip55c3-sp12-commercial-risk-and-legal-domain-work-to-support-sf-001-expanded-mandate-related-to-rwas/18943)". Excited for this one and will be following the results closely.

>Review each existing RWA collateral, determine if risk parameters are appropriate, recommend changes to MKR holders if necessary
>
>Monitor and create reporting for existing RWA vaults
>
>Collaborate with community regarding how the RWA Council should oversee MetaDAOs - design constraints in collaboration with ALM contributors to ensure ample liquidity under significant market stress
>
>Commercial and legal assessments for community approved RWA collaterals as needed
>
>Review of the legal structures
>
>Review of the resolution, wordings and workflow
>
>Review of the agreement between entities and service providers
>
>Writeups of Legal Structure and Governance Appropriateness Verification
>
>Other open legal review questions identified along the way
>
>Commercial risk analysis: including but not limited to sponsor or arranger risk, credit risk, concentration risk, servicing risk, etc.
>
>Review of the commercial structure: flow of funds, leverage profile, credit enhancement, servicing mechanics, scaling/ramp-up/utilization structure, reps/warranties/covenants
* January 5 : "[Parameter Changes Proposal - PPG-OMC-001](https://forum.makerdao.com/t/parameter-changes-proposal-ppg-omc-001-5-january-2023/19327)". A variety of adjustments to stability fees and system risk parameters. Most noteworthy here is the decision to increase debt ceilings on Aave and Compound D3Ms, which I disapprove of, though it remains low. Aave and Compound introduce additional risk to the DAI backing that is in my eyes unnecessary. MakerDAO lacks the capacity to monitor governance and collateral risk in these markets and respond appropriately to a sudden change in risk conditions. There is no mechanism to safely mark down bad debt in one of these markets, and it's likely a manual emergency governance intervention would be required were this to occur. While major bad debt on Aave or Compound may sound absurd to some, it is far from impossible.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>