# A Letter to MakerDAO

Dear MakerDAO,

You're my favorite DeFi project -- I set out to build Volt Protocol after looking at MakerDAO and wondering at length how to properly scale it. I knew it was unrealistic to expect MakerDAO governance to put the ideas of an outsider like me into practice! As it should be. Experiments are for the edges.

Dear MKR holders,

I'm sad to see that today MakerDAO and DAI are on a precipice -- on one side, sustaining its current dominance as the preeminent decentralized stablecoin and growing to serve tens of billions of dollars in holder demand at a healthy profit, remaining a central pillar of DeFI. On the other, insolvency and ruin due to reckless financial engineering.

# Like Recognizes Like

I know what it feels like to have a manic, totalizing vision. To be sure that you've seen and understood the problems of a system, and that if it can all come together according to your master plan, you can make it all right. You just need these other people to fall in line or get out of the way.

The trouble is, what if you're wrong?

To Rune, state actor censorship is the number one threat and concern to deal with. At first he hoped that focusing MakerDAO on "clean money" initiatives would get in the good books of regulators. Now his common refrain is (in my words) "MakerDAO can't make DAI blacklistable, so it's impossible to operate compliantly, therefore we must plan to maximize censorship resistance long term above all other values".

Unfortunately, his proposed solutions have a far higher likelihood of destroying MakerDAO and DAI than any hostile regulator. Please don't take this the wrong way -- I don't have all the answers and would be humbled by the responsibility if I actually were in a position to implement changes in a system handling billions in user deposits. It's precisely that sense of hestitation that compels me to urge caution toward 'perfect' plans.

# Asset Liability Mismatch

The Endgame plan is a chimera, with the Protocol Owned Vault being the clearest failure point. The proposal is to use the surplus buffer to buy ETH or staking derivatives, and, so long as 'Pigeon Stance' persists, to use as profitable of RWA backing as possible for DAI to accumulate more ETH with the rewards.

This is fine enough, though using your emergency reserves for speculation isn't what I endorse. This ETH is on top of the DAI backing which consists of either overcollateralized user vaults, or USD-denominated PCV. When your main risk is incurring a USD-denominated shortfall, it makes sense to keep your surplus in USD or USD-denominated rather than ETH. Maybe the DAO will get lucky and have a good investment, maybe it will be forced to sell ETH at a major loss when the surplus is called upon.

Either way, these are acceptable outcomes. Better to sell ETH reserves than to mint and sell MKR, a less liquid asset.

The real problem begins when MakerDAO mints DAI against ETH in the POV and uses it to take leverage. This puts Maker, by design, on a journey to be a FEI-like system where a meaningful portion of the supply is backed by protocol owned ETH or derivatives. [Read for yourself in the Maker forum](https://forum.makerdao.com/t/mip84-activate-protocol-owned-vault-emulation/17713?u=onetruekirk).

It is simply **not possible** to safely back a dollar denominated liability with ETH and its derivatives at scale. Overcollateralized user vaults are safe, but have limited demand, so require another source of supply generation lest they remain niche and vulnerable to upward (aka, surpise interest rates for the borrowers).

A protocol owned vault is the road to ruin. Consider a situation in which 10% of a 5B DAI supply is generated against collateral in the protocol-owned vault, and the remainder is deployed in real world assets. We'll use 225% collateralization as in Rune's proposal. If the value of ETH declines by half, MakerDAO will need to sell ETH to buyback 5% of the DAI supply to maintain target protocol-owned vault collateralization. This could easily lead to losses of $500m.

# Really, more new tokens?
MetaDAOs are a belated attempt at getting in on the yield farming game, hoping for an audience of greater fools to finance expansion of enterprises with no obvious durable profit potential. MakerDAO is better than this! Emissions schemes are not what's needed to drive scaling and further decentralization.

## Why not offer something real to users instead
A credible commitment to an active DAI Savings Rate would go so much farther to grow MakerDAO than any subDAO token. You'll then see DAI become the preferred PSM backing for all new decentralized stablecoins like GHO or VOLT. SavingsDAI would also become the preferred backing for fixed rate products, with greater depth than markets like Compound or Aave.

# ETHERDAI is a good idea
Out of all the Endgame components, the only one that strikes me as a strong direction is a Maker ETH derivative. This can be cross sold to the existing DAI holders and is a natural move for a stablecoin issuer. Frax has done the same and others may have such ideas in the works (😉).

If we think ETH is money, launching an ETH-denominated debt unit/credit money seems like a natural step. ETHERDAI and the like do not have to correspond 1:1 with a liquid staking derivative. They can incorporate other sources of yield such as lending, and offer a better liquidity profile with PSM minting and redemption.

# A Plea to MKR holders
First of all -- reconsider support for the Endgame plan if you have not already done so. MKR holders will regret if they choose to back DAI with protocol owned ETH, or if they hold the surplus buffer entirely in ETH against potential dollar-denominated losses. It would be a shame to see them squander the cultural and economic moat DAI has so far established. The wrong decisions might look okay at first, until the day when destruction comes.

If I'm preaching to the choir, yet the forces of chaos and madness prevail, consider getting involved with our work at Volt Protocol. The goal is similar to Reflexer/RAI's mission of ungovernance, though we recognize it's not so simple to ungovern an evolving complex system like DAI or VOLT. Market governance strives for an incentive aligned way to decide how PCV is deployed among venues, and uses market rates to price both capital supply and allocation.

# An Appeal to DAI holders

We've recognized that a sharp distinction between "stablecoin" and "governance token" is a mistake. Can anyone doubt that, if DAI holders could veto a planned depeg, they would do so? If they could choose between the risk of a protocol owned vault and the steady yield of RWA passed on through the DSR, which way they would choose?

Lido is in the process of innovating in the area of dual governance ([I owe a response in the thread!](https://research.lido.fi/t/ldo-steth-dual-governance/2382)). Volt Protocol will do the same by granting veto rights to VOLT holders. This way even if I or other governance token holders are struck by a dangerous notion in the future, VOLT holders can protect themselves.

If this interests you (along with an always-on DAI savings rate, as we believe in yield by defaut), join the conversation in [our community forum](https://community.voltprotocol.io).

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>