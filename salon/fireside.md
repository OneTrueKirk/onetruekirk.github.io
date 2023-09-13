# Morpho Fireside Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This article is reviewing [the thoughts](https://variant.fund/articles/building-a-truly-scalable-lending-protocol-morpho-at-ethcc/) [Geoff Hamilton](https://twitter.com/gham1lt0n) submitted along with his interview of [Paul Frambot](https://twitter.com/PaulFrambot?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) from Morpho. Regular readers will know I have reviewed Morpho previously and am fond of their team's thinking despite some differences in our approach.

## Decentralized brokers vs protocols

Paul proposes a definition distinguishing a protocol like Uniswap, which has no control over its users risk level, from a "decentralized broker" like Aave, where tokenholders or delegates manage risk on behalf of more passive depositors.

Where I disagree with Paul is on the following claim:

>Paul makes a strong case for why decentralized brokers are not the future of DeFi lending: they are not trustless, efficient, or able to reach scale. He explains why protocols are a better structure for lending markets at scale and lays out an approach to building and scaling a lending protocol.

My personal focus is on how to build a more trustless "decentralized broker" than exists today, [more on this here](https://onetruekirk.github.io/dao.html). I'm agnostic about whether dominant markets will primarily use bespoke lending contracts, or shared based layers. However, it's too soon to give up on a decentralized broker that is trust minimized, highly scalable, and efficient. Paul says that decentralized brokers can't scale to handle trillions. Bold as it may seem, I would make the opposite claim -- not just one but many decentralized brokers will eventually reach trillions of AUM and outcompete legacy financial institutions. Each of them will need to have a powerful, cohesive community and brand over a long period of time. Each of them will seek to obtain 'edge' over its competitors, including developing distinctive smart contracts and interfaces. Very likely, they will be among each others' largest customers and have shared liquidity.

## Thought experiment

Let's say a certain lending market on Morpho's base layer is very popular, but its operators begin to make increasingly dangerous risk decisions. The MORPHO holders become concerned and take action to delist it from the frontend and warn users. Nonetheless, the market blows up and many users lose money. How much damage does Morpho take from this, and how much does it gain from well-behaved pools on the base layer? These issues were frequent topics of conversation at Rari Capital. There are many ways to correctly implement smart contracts for lending, but there is none that is foolproof against bad risk managers. I'm curious to learn more about how the Morpho Community will present risk to users, as well as what choices will be made about distribution of MORPHO tokens in independently governed pools.

## A middle ground

I wonder about the idea of MORPHO tokens holding various checks-and-balances powers within the pools built on their platform. For example, blocking the onboarding of a new collateral to a pool, but not being able to add one. This would position the Morpho DAO as a sort of regulator over its platform, but would not give it the powers to rug pools operated by others.

## Conclusion

Decentralized broker vs protocol no longer looks so black and white -- there are token communities that control frontends, those that control risk parameters, and possibly a wide spectrum in between. I look forward to seeing Morpho's new products come to market, as it seems there is more in the works than has thus far been revealed.


<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>