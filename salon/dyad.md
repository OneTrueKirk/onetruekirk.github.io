# DYAD Stablecoin Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews here. You can comment below with your own thoughts. This article is reviewing the DYAD stablecoin, submitted by founder [Joey Roth](https://twitter.com/joeyroth). Link to original submission [here](https://www.notion.so/dyadstable/DYAD-SSOT-441278f1a75c4760bbd0cac5dc8505bb?pvs=4
).

```
Strategically composing a collateral basket and managing the DYAD debt drawn against this basket is the fundamental DYAD gameplay. 
```

## Overview of DYAD

Holders of a membership NFT can deposit collateral tokens into vaults and mint a deposit receipt token, XP, which must be burned to withdraw their collateral. They can borrow DYAD against their collateral, and they can also stake their XP for up to four years to earn more XP. During the lock, they can still borrow or repay their loan, but not withdraw their collateral.

## Stated Design Goals

```
DYAD is the first modern stablecoin: backed by diverse uncorrelated collateral, with carry cost less than its $1 peg. This matters because stablecoins live and die by the laws of unit economics. 

It transcends the decentralization vs cost dilemma by moving beyond the isolated collateral pools of the traditional CDP and the funding rates and centralization of newer delta neutral designs. 

DYAD achieves this through shared collateral pools that dNFTs (DYAD NFTs) fund as they compete for the lowest DYAD mint cost, moving closer to this goal as they contribute to the protocol’s size and stability.
```

DYAD sets out to acheive a higher effective decentralization than DAI, while being more efficient than LUSD. Let's see how it measures up.

## Efficient Redemption and Liquidations

The protocol allows DYAD holders to redeem for "$1 of collateral" from any of the active vaults with a dynamic redemption fee that varies per vault. This is analogous to Liquity's redemption feature, but on a per-vault instead of per-position basis. I like this model, since it provides a strong protection against downward depeg without requiring active liquidity management by governance.

The liquidations also remind me of Liquity's stability pool, but where all collateral depositors are in the stability pool for their own vaults by default.

These two aspects are my favorite part of the design, and I'll take inspiration from them when thinking about different types of callable loans in the future.

## Governance

```
The immutable Social Licensing Layer (SLL) controls a Vault's license to comprise part of dNFT collateral baskets- in other words, to start partially backing each DYAD token. This social layer is thus responsible for fundamentally securing DYAD itself, since malicious vault contracts and/ or collateral could depeg DYAD if allowed to comprise part of its backing. The bar is high - we accept tremendous friction in onboarding new collateral in exchange for security. 

The SLL is best imagined as a bank of on / off switches, one for each dNFT, that the SLL contract appends to any other contract whose on-chain address is permissionlessly submitted to the SLL contract. Each dNFT controls the position of one switch per vault candidate (which can be any contract deployed on mainnet). When a vault candidate achieves a 2/3 supermajority of their SLL switches set to the “on” position by the dNFTs, the vault can be part of dNFTs’ collateral baskets.

dNFTs can change the position of their switch in any vault at any time. Vaults lose their license to back DYAD and their allocation of claim fees if their portion of “on” switches dips below 2/3.
```

Oboarding and offboarding vaults is the key governance action, requiring a 2/3 majority of dNFTs voting in approval at any given time for a vault to be added. Depending on how the dNFT supply is distributed, this is quite a high hurdle to clear. It doesn't seem likely that DYAD can support a higher collateral diversity than classical token governance given the high quorum requirement.

## Revenue

```
- 10% dNFT claim fees
- 1% collateral withdrawal
- 3% liquidation fee
```
The submitted article does not specify the dNFT minting or claim mechanism, so I'll set that aside for now. Short term borrowers pay long term borrowers in the form of XP dilution as well as the withdrawal fee. The risk taken by long term borrowers depends on the collateral of the vaults they are using.

## Sybil

```
Equity Control: The term $\left( \frac{1}{1 + \left( \frac{XP_{\text{dnft}}}{XP_{\text{total}}} \right)} \right)$ ensures that if a user already has a big portion of the total XP in the system, their reward rate slows down. This way, no single user can dominate the rewards and newcomers still have a fair chance.
```

I'm skeptical of the utility of this feature, since one user can obtain more than one dNFT, but the severity of Sybil risk depends on how dNFTs are issued.

# Conclusion

The redemption and liquidation mechanisms proposed for DYAD are worthy of attention for lending market designers, and I greatly enjoyed thinking them through. I'm skeptical that the "XP game" alone is enough to drive borrower adoption, and also wonder about how DYAD holders will earn yield, or else what demand sources are anticipated. To Joey, thank you very much for your submission, and I look forward to in person discussion.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>