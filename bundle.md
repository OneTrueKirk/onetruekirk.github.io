# Scale your Cake and have it Immutable, too
Today's prominent rollups are bound by an unfortunate tension. Their purpose is to minimize trust assumptions beyond those present on the base layer, yet they seek compatibility with the Ethereum Virtual Machine, a moving target, so they must be upgradable.

Many compromised on decentralization to go faster to market, restricting fraud proof submission to a whitelist or launching without them, as discussed recently by the [Twitterati](https://twitter.com/rauljordaneth/status/1691852822185136144?s=20). Note that permissionless fraud proofs for an upgradable system are a [hard problem](https://medium.com/infinitism/optimistic-time-travel-6680567f1864). See [L2Beat](https://l2beat.com/scaling/summary) for a good overview.

Is there another way?

![img](intofuture.jpeg)

## Immutable Code, Mutable Parameters
The alternative is to embrace compatibility only with the current version of the EVM, or discard EVM compatibility entirely. Starknet made the latter choice despite remaining upgradable. From an application perspective, a simple immutable architecture built to purpose appears attractive.

I've discussed [related concepts](https://onetruekirk.substack.com/p/decentralizing-credit-201) before. This article is a first attempt to synthesize those ideas into an initial scaling system for borrowers.

A few properties we would like to maintain:

### Unified liquidity
Borrowers on the rollup should not be limited to liquidity explicitly deposited on the rollup by users. If you have ETH collateral on the rollup, and want to leverage long ETH, you should be able to atomically enter that position without being limited to rollup AMM liquidity or something of that nature. Likewise, if you start out with CREDIT, you should be able to swap into any of the available collateral tokens up to the limits of mainnet liquidity.

While net withdrawals from an optimistic rollup are not permissible without waiting for the challenge period to pass, it's possible to use mainnet collatersl to borrow tokens from the rollup. This permits an interaction like the following:

I start out holding some CREDIT on the rollup in the CREDIT Savings Rate. I decide I want to long ETH, so I sign a message stating the price I am willing to swap at, with an expiration date, and send it to a solver, or perhaps I broadcast a [Dutch order as on UniswapX](https://blog.uniswap.org/uniswapx-protocol).

In either case, someone fills my order by "zapping" into a debt position borrowing CREDIT against ETH collateral on mainnet, and then bridging the *debt position ownership* from mainnet to L2. There, they swap their collateral, ETH, for my CREDIT, and repay their debt, before bridging the proceeds back to mainnet.

The same operation works the other way. If I am instead selling ETH, the market maker will enter a long CREDIT/ short ETH position on mainnet, bridge it, fill my order, repay their debt, and bridge out the profits. The market maker may keep some inventory on both layers, and will fill orders of more than one user at a time at maturity, so they need only access leverage to fill the net demand that the former sources cannot satisfy.

This eliminates the need for trusted bridges to perform fast arbitrage. A market maker can obtain leverage to fund their arbitrage activities while performing fast swaps, and need only wait for the withdrawal delay to realize their profits, not to close the trade.

This mechanism enables liquidations to be performed on layer two even if the collateral has no liquidity there, since the underlying tokens can be borrowed on mainnet and sold even when their ownership claim is on L2.

### Permissionless block proposal
We don't want liveness to be compromised under any conditions, which could be fatal for loan health. This means a [based rollup](https://ethresear.ch/t/based-rollups-superpowers-from-l1-sequencing/15016) model is preferred. As you might expect, the proposer must be required to stake some amount of capital, which is slashed if a challenge succeeds, while a challenger must post a lesser bond if they wish to make a challenge, which in turn will be slashed if their challenge fails. The original proposer's slashed capital can be split between the challenger and the protocol (if the challenger got 100%, one could challenge their own proposed blocks to grief the system).

There's no magic number for how much capital, but it needs to be enough that griefing the protocol to delay finality (and keep users from withdrawing their funds) is infeasible, and any such attack cannot inflict damage due to delaying liquidations or similar. For example, if the longest successful challenge takes a week, a few % of the TVL in bond is sufficient to be the proposer, since an attacker would burn an enormous amount to keep user funds hostage for a few weeks, and cannot seize funds so long as there is any willing challenger. The shorter the maximum time for a challenge, the less of a bond is needed, since the higher the cost to grief over a given time period becomes.

It should be our goal to reach a short challenge time and a minimal proposer bond. Specific parameters must be validated through simulation and adjusted as the amount of funds at risk and the composition of the lending terms changes, or as changes occur in the base layer such as block time changes.

### Minimal value leakage
GUILD holders make their living by staking on lending terms. There is no need to extract further value from rollup users. This is harmonious with the based rollup mechanism. Reducing MEV to the minimum requires intelligent behavior by users. Swap transactions accessing mainnet liquidity should be sent through a suitable system like Flashbots, possibly taking advantage of the mechanism I described above in the section on liquidity. Liquidations proceed by auction to return the maximum amounts to borrower and lender respectively. At the rollup level, this means account abstraction. L2 state changes have their mainnet cost paid for by the proposer, which can fill intents in any asset pair, no matter whether ETH is one of those assets. Expecting users on layer two to continually top off their ETH supply to perform transactions is *like, so 2021, man*. It costs them time and money. This means the rollup itself has **no enshrined fee mechanism**, users can offer whatever they want to proposers who make the choice whether to include, and some proposers may offer privacy or certain ordering guarantees.

