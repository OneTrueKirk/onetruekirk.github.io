# Llama
## Submitter: Shreyas Hariharan

This is a peer review article as part of the second Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This article is reviewing Llama, a governance framework for protocols on Ethereum and other EVM chains, submitted by [Shreyas Hariharan](https://twitter.com/HelloShreyas
). See the repository [here](https://github.com/llamaxyz/llama).

Blurb from Shreyas:

>Llama is an onchain governance and access control framework. We were active contributors to lending protocols like Aave and built Llama partly in response to how risk parameter updates worked in legacy systems.

## The Devil is in the Details

The governance question is near and dear to my heart. Frankly, I wish Llama had been complete and available when we began the Credit Guild design process. Where we focused on designing a better lending market, with a heavy emphasis on the role of first loss capital, they created a more general framework for modular governance. Several of the features we included in our market, like distinct timelocks for separate system actions, multi-token veto, and a Guardian with limited powers, would be easy to replicate using the Llama model. There is a lot of merit to using shared, standard frameworks where possible, to get as many eyes on the same code as possible and minimize errors.

To understand why frameworks like Llama are important, it helps to think about the history and current landscape of DAO governance. Broadly, we can break down all protocols into the following set of categories:

* core protocol immutable, offchain coordination around incentives and upgrades (Liquity, Ajna)
* offchain-appointed multisig control (Optimism, Frax)
* elected council control/on-chain token voting election of multisig members (Arbitrum, Synthetix)
* monolithic token voting (Aave, Compound)
* dual governance (not yet implemented in production by them, but popularized by Lido)
* Modular governance (some types of decisions require token vote, others a multisig can perform, etc). Pioneered by Tribe DAO among others

I will assume that the reader is a fellow decentralization enthusiast, and thus does not approve of multisig governance except in the earliest stage of a protocol's beta phase. We will also set aside debates around immutability for the purposes of this review.

Most protocols today either require a quorum of *all* tokenholders for *every* adjustment of parameters in the system, or defer to a relatively centralized group of delegates or elected council members for these decisions. The former suffers from voter apathy, while the latter reintroduces the very centralization and trust assumptions that DeFi strives to prevent.

"Dual" (maybe better termed "multiparty") governance allows multiple types of stakeholders to express themselves. Modular governance recognizes that *certain kinds* of changes should require a vote by all holders or a longer timelock, while *other kinds* can be performed immediately by an elected council or by a smaller quorum.

Llama makes it easy to design modular governance systems where each type of system action has appropriate controls, and where a variety of stakeholders can have appropriate powers. The precise configuration should be different for each protocol, but a shared framework increases legibility for tokenholders, delegates, and users alike.

Llama strikes me as an ideal candidate for retroactive public goods funding from Optimism and others. I could rattle off a long list of protocols that would benefit from adopting a common framework and investing in shared security. While we've already created a bespoke configuration for Credit Guild using OpenZeppelin AccessControl/Governors/TimelockControllers, we will investigate using Llama in future versions or when we create distinct governance flows for additional parameters.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>