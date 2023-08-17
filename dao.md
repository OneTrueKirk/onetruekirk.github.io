# Decentralized Autonomous Organizations and Risk Management
>The ten thousand things rise and fall without cease, Creating, yet not possessing, Working, yet not taking credit. Work is done, then forgotten. Therefore it [lasts forever](https://www.penguinrandomhouse.ca/books/97893/tao-te-ching-by-lao-tsu-translated-by-dc-lau-introduction-by-sarah-allan/9780679433163/excerpt).

![img](dao.png)

Written in response to [this article](https://morpho.mirror.xyz/F652srnxjv4qsIEHLUrDwOvrYgXU8p0io2cNogb2BJY) published by Paul Frambot of Morpho Labs. Paul's article does a fair treatment of the successes and failures of the first generation of major onchain lending markets like Aave, Compound, and MakerDAO. He covers both benefits and downsides. I found this passage particularly striking:

>Aave, in particular, is an interesting case study of the promise of decentralization vs. the hard realities of risk management. Aave has more than 500 different risk parameters that need to be monitored in real-time and updated almost daily. More risk parameters must be monitored and adjusted as more features and markets are supported. There are no real economies of scale here – risk management complexity grows with the number of user options available.
>
>Token holders can be anyone, and they are not necessarily risk experts. While a small number may be knowledgeable in what is a (very) complex field, it’s safe to assume that the majority are not. Yet, they collectively manage all the 500 interconnected risk parameters protecting billions of dollars in real-time.
>
>As a result, the ongoing management of these risk parameters falls to trusted third parties that make recommendations to the token holders, who typically green-light anything other than the most controversial proposals.
>
>Even if these outside risk management consultants make ethical, sound recommendations, it’s easy to imagine the opportunity for conflicts of interest between the firms, token holders, and end users. Or, at the very least, see how consensus can slow down the management of live risks.
>
>Tl;dr: Effective risk management demands both expertise and the ability to make quick decisions. By definition, DAOs do not suit this role.

## a word on definitions

What is a DAO (decentralized autonomous organization)? While the acronym is used 11 times in Paul's article, he does not provide a definition, so I will take the liberty of advancing my own: `a decentralized autonomous organization, in the context of Ethereum, is a collective whose membership is determined by token ownership (whether fungible or otherwise, transferable or no), and which uses some form of governance or voting to control smart contract systems or real property`. This is a broad description, intended to include everything from Ajna, which will only be voting on grant allocation, to Aave, which controls 500+ discrete risk parameters with token voting, to Lido where stETH holders eagerly await veto rights, to Frax where historically a multisig has had full control, but Snapshot votes have been faithfully carried out.

The classic DAO, which requires a substantial quorum and majority vote of tokenholders to make any parameter changes, and where any governance vote may be existential due to the scope of its powers, faces obvious strains managing even a handful of collateral assets, let alone dozens or hundreds of unique lending terms. This is hardly the only mechanism that fits the label of "decentralized autonomous organization", though.

## nuance in governance

I quit my job two years and change ago to address this precise problem, working toward a more scalable parameter control process that I call market governance, summarized briefly as "under token-voting governance, with 51% of the tokens you have 100% control of the protocol. Under market governance, with 51% of the tokens you have 51% control of the protocol". You can read more about our system [here](https://github.com/volt-protocol/ethereum-credit-guild). The protocol is open source and nearing code freeze now. All review and feedback is appreciated.

Rather than focusing on our particular implementation, the point I would like to make is that while Paul is right that "effective risk management demands both expertise and the ability to make quick decisions", smart contracts offer enormous potential in reducing the harm a rogue risk manager could cause and ensuring credible neutrality is maintained. Each parameter that needs to be governed demands a suitable mechanism, with permissions and latency such that participants in the system have time to respond to changes where required, or safeguards to ensure alterations of terms are fair to both borrowers and lenders.

It is possible that these safeguards can be built on top of a singular base lending primitive, but I suspect that this will mean convergent evolution rather than universal use of a shared onchain instance. Developing a "correct" and fully expressive mechanism for lending is one important piece of the puzzle, but better handling of each type of governance decision is also "core" to a well-functioning lending market. 

The governance of a market like Compound is both too strong (able to make arbitrary code changes such as the one that froze the cETH market), and too weak (unable to make day to day tweaks in interest rates to remain competitive with peer markets). While the idea of multiple risk managers using the same underlying market code makes sense, we would also like to see that code improved, and the control levers made as granular as possible. For example, it makes sense for a risk manager to be able to tune the base rate of an interest rate curve daily within a limited bound, while arbitrary code changes are better off either impossible, requiring a large quorum + vetoable by a security council, or similarly restricted.

## wait, it's all latency?

To decide on how a particular process should be governed, we should think about:

* is it adversarial? Who stands to gain and who stands to lose?
* is it urgent? Is there a risk to inaction?
* is it dangerous? Could a mistake lead to losses, such that there is a major risk to action?
* is it frequent? How often does the same type of change need to be made?

Only if *all* of these factors align should parameters be subject to the same governance process. In most cases, they should be distinct.

Consider a spectrum from liquidation, to interest rate adjustment, to allocation of debt ceilings, to offboarding of collateral, to onboarding of collateral, to adjusting the code used to perform auctions. With each step, we need to perform the action less frequently, while some of the actions are urgent, others are very dangerous. Handling all of these in the same way is inappropriate. A key limitation is that a certain minimum time is needed for participants to become aware of and react to changes. Governance probably shouldn't have the power to raise interest rates to 100,000% on existing borrowers, since they may not notice and be liquidated, but there must be a way to "call" loans such that the positions are closed without penalizing borrowers, in case the collateral risk changes and lenders need protection. Users aren't capable of evaluating frequent code changes, so these should be either impossible, or limited to a certain frequency. Interest rates should adjust often according to market supply and demand, and it should be possible to make small tweaks to them often in response to competition among lenders.

## tldr

There are at least three interesting directions in lending markets:

* parameter automation (use a controller to adjust rates rather than a static curve)
* unbundling (use shared immutable smart contract primitives, open source risk models)
* mechanism reform (make loans callable, add granular governance, better handling of duration)

I am encouraged by innovation on all three fronts, both in [existing markets](https://governance.aave.com/t/lending-market-improvements-irm-automation/14070) and [new ones](https://www.ajna.finance). My hope is that we can reduce some of the points of failure in the industry before they come to bite us, especially the risk of market manipulation attack on widely shared oracles, and the risk of liquidity crises where global debt is not taken into account by lenders.