<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>
# Against Token Plutocracy

![img](solid_gold.jpeg)
>the golden rule: he with the gold, rules?

"51% attack" is a familiar phrase to many cryptopians, but really, every governance proposal today is an "attack" in which a majority imposes its wishes over any dissent. There is no nuance or compromise, the winner takes all.

Vitalik has [a great article here](https://vitalik.ca/general/2021/08/16/voting3.html) explaining various problems with naive token voting, and exploring many of the directions for alternatives that interest us at Volt Protocol.

The article lays out various major problems with token voting, most notably, **incentive misalignment** and the risks of **vote buying**. Vitalik calls out principle-agent problems, where governance token holders are able to act in ways not aligned with the interests of users, or where expert committees to act in ways not aligned with the interests of governance token holders, as well as coordination problems, where it may be difficult to coordinate certain categories of users around needed actions, as when voters face a cost to vote but see no benefit vs passive free riders, or are insufficiently knowledgeable to wisely discriminate between options and would benefit from delegation or committees.

A few notable passages:

>A token in a protocol with coin voting is a bundle of two rights that are combined into a single asset: (i) some kind of economic interest in the protocol's revenue and (ii) the right to participate in governance. This combination is deliberate: the goal is to align power and responsibility. But in fact, these two rights are very easy to unbundle from each other

>Coin voting fails because while voters are collectively accountable for their decisions (if everyone votes for a terrible decision, everyone's coins drop to zero), each voter is not individually accountable (if a terrible decision happens, those who supported it suffer no more than those who opposed it). Can we make a voting system that changes this dynamic, and makes voters individually, and not just collectively, responsible for their decisions?

Some decisions are Judgements of Solomon where an acceptable compromise is impossible, such as whether to deploy the Uniswap code on a new chain. You can't deploy it halfway. It's hard to imagine a credibly neutral way the results of the decision could be measured and used to punish or reward voters.

On the other hand, for governance of lending protocols and stablecoins, there are many types of system actions that lend themselves well to granular control. For example, the collateral factor of ETH on Compound is not a binary yes/no, nor are the relative debt ceilings of the various collateral assets on MakerDAO. These parameters are amenable to control by guage style voting with skin in the game, as failures or successes can be transparently observed on chain.

Instead of choosing between :

"YES -- onboard cbETH as collateral to Maker with a 10m DAI debt ceiling"

and

"NO -- do not onboard cbETH",

MKR holders would simply have the option to stake to whichever collateral token they prefer. If 5% of staked MKR votes for cbETH, its debt ceiling would equal 5% of the DAI supply. When some of the MKR holders change their votes, debt ceilings are adjusted accordingly. 

While I use the example of Maker for the sake of familiarity, really I am thinking of Volt Protocol, and a similar approach can be used whether the protocol is allocating funds among other integrated venues (lending externally in Compound or Euler), allocating among PCV backing (like Maker holding a tokenized ETF), or setting debt ceilings for certain collateral assets.

I call this style of system "market governance".

## Quadratic Governance Cannot Be Totally Open and Decentralized

One major class of alternative to majority-rules token voting that has gained traction is proof-of-personhood and quadratic voting. This is unsuitable for a trustless open economic system since there is no credibly neutral way to verify real personhood at scale, but is likely highly relevant for more hands on, membership style DAOs which can admit some trust in the member set.

## Optimistic Governance Harmonizes with Market Governance

Optimistic governance, as pioneered by Fei Protocol, meshes well with the market governance model. As noted above, there are some questions that market governance cannot answer, such as "yes/no, is this upgrade to core protocol code allowable"?

Vitalik proposes building "fork friendly" systems, but it is difficult to imagine how one would properly fork DAI and fairly engage the DAI holders in the decision making process. Instead, I favor an optimistic governance approach with checks and balances from multiple voting classes and distinct quorums for different purposes.

For example, it's common for protocols to have a certain quorum threshold for a vote. This can be made more nuanced by making separate positive and negative consent, ie, you need at least 10% of the supply to vote yes on a proposal for it to pass, but if at least 20% votes no, it can't pass no matter how many tokens vote in favor.

Likewise, the stablecoin holders themselves (in the case of a protocol like Compound, the cToken holders) can hold veto rights over code changes, so they are able to protect themselves without being forced to exit.

These measures mitigate the danger of vote buying, as they make it possible to pass uncontroversial proposals even with a modest quorum, but impossible to pass malicious proposals without obtaining a supermajority of the token supply.

There's a great deal more work to be done in this area, and I'm keen to discuss with anyone who is working along these lines. For example, in [conviction voting](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475), a proposal gradually accrues power over time as voters remain committed to it. This could be combined with a veto module to adjust thresholds based on how much of the supply is for or against over time, and involve multiple user classes. If you're interested, please get in touch.

## Restrict Governance Where Possible

Vitalik mentions several approaches to limit the powers of governance:

>Use on-chain governance only for applications, not base layers: Ethereum does this already, as the protocol itself is governed through off-chain governance, while DAOs and other apps on top of this are sometimes (but not always) governed through on-chain governance
Limit governance to fixed parameter choices: Uniswap does this, as it only allows governance to affect (i) token distribution and (ii) a 0.05% fee in the Uniswap exchange. Another great example is RAI's "un-governance" roadmap, where governance has control over fewer and fewer features over time.
Add time delays: a governance decision made at time T only takes effect at eg. T + 90 days. This allows users and applications that consider the decision unacceptable to move to another application (possibly a fork). Compound has a time delay mechanism in its governance, but in principle the delay can (and eventually should) be much longer.
Be more fork-friendly: make it easier for users to quickly coordinate on and execute a fork. This makes the payoff of capturing governance smaller.

I've been variously publicly critical and admiring of systems like RAI which take this to an extreme. Realistically, a system like MakerDAO cannot have human input entirely removed. Those systems that attempt this have defaulted to trusting the Chainlink network to govern them.

As you can see, we plan to take "limit governance to fixed parameter choices" a step further, with the idea of separate governance mechanisms for parameter tuning (which can be entrusted to market governance) vs arbitrary code changes. As a protocol matures, the quorum requirements for arbitrary code changes can be made increasingly strident, while the parameters governable in a fluid market governance style will become better defined.

Bringing back the MakerDAO example, a governance flow might exist where collateral could be onboarded "permissionlessly" with a modest MKR quorum, and its debt ceiling based on continuous staked token voting, but a hefty 50% quorum is needed for code changes in the system with a major time delay.

## Conclusion

There's not much new under the sun as far as ideas for how to build more robust decentralized systems. If you enjoy this sort of thing, go trawl old blog and [Ethresearch posts](https://ethresear.ch/t/votes-as-buy-orders-a-new-type-of-hybrid-coin-voting-futarchy/10305?page=2). What's hard is rejecting the bad ideas and implementing the good ones safely, cost effectively, and expediently. If you have comments, suggestions, or criticisms, I would love to hear from you below or on Twitter.

p.s. : The special form of ragequit linked in the Ethresearch post above is intriguing, but relies on a trusted price oracle, so it doesn't add up for me.

<script 
        src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>