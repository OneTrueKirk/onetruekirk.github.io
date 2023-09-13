# Pharos Lending Market Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews here. You can comment below with your own thoughts. This article is reviewing the [Pharos lending market](https://docs.pharosprotocol.com), submitted by [mod323](https://twitter.com/itsmod323).

## Overview

Pharos is a highly customizable lending system that uses shared plugins, meaning that sets of lending terms can be created to suit the needs of one or many lenders and borrowers using the same code. Responsibility for risk lies in the hands of the end user, for example, making sure the pool's oracle is safe, or that its interest rate model is competitive. There is no central governance to manage risk.

## Comments

I haven't done diligence into the smart contract security, which is perhaps the most important differentiator among long tail asset lending markets. I really like the following feature:

>Users can limit who is able to fill their offers based on filler address. This allows for private lending without the need for a human broker. Sounds pretty boring at first, but it is easy to imagine several use cases for this functionality.
>
>One user can offer a unique set of loan terms to another user. Perhaps because they pre-negotiated the deal irl and want to execute the agreement on-chain.
>
>Institutional lenders could create large supply markets and restrict fillers to users who KYC with them. Enabling compliance with the lender's legal requirements.
>
>A protocol can offer unique lending terms within their community. Perhaps it is discounted lending rates on protocol assets to their users, or an in-house valuation on using NFTs as collateral.

This seems like valuable infrastructure for a protocol trying to become a major venue for OTC or long tail lending. Combined with a custom liquidation mechanism (for example, taking direct possession of the collateral) it's possible to enter into trust-minimized loans between large private parties. I'll have to consider whether it would be useful in the Ethereum Credit Guild lending term model. Likewise, maybe a callable loans option for Pharos would be interesting.



<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>