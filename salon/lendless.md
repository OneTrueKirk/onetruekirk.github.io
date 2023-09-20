# "The Stablecoin Trilemma" Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This post is reviewing the [Lendless borrowing platform](https://docs.google.com/document/d/1nal02PkwB61OQkc8RNE1isLzVDiwgKQa1YvjeWjzJwM/edit) submitted by [Fishy](https://twitter.com/FishFishDeFi).

## Overview

While the Ethereum Credit Guild relies on the set of GUILD holders to set lending terms and allocate liquidity, Lendless allows open market competition between lenders, combined with a **multiplier** that varies per asset. A lender might deploy 1m of their own capital to lend against ETH, and the protocol would mint 5m in the LEND stablecoin in available debt ceiling. Like the ECG, proposed loan terms can be challenged. Unlike the ECG, the challenge is not a direct veto, but an economic challenge. Let's say that ETH is worth $1000, but I propose to lend $2000 per ETH, and put up 1m of my own capital. If challenged, a trader can optionally sell me ETH at twice the market price, so I bear the consequence of the mispricing.

I like this design because it makes it easy for a wide set participants to offer terms for loans, similar to Ajna, without giving up on the idea of passive lending. The downside is that you can only effectively challenge a proposed lending term if it is **currently underwater**. This means there isn't a strong way to protect against risky but currently sound terms that may carry a risk of liquidation failure in the future, or terms that have mispriced interest rates but are nontoxic.

## Questions

>This multiplier is determined depending on the risk associated with the collateral. 

The Lendless protocol has minimal governance needs, but it's not clear to me how the multiplier per asset is set or adjusted. There's no governance token described, so maybe the LEND holders would have to vote, or a risk committee would have this limited power.

Relating to my comments in the overview section, the challenge method Fishy has described seems correct for protecting against loans that are underwater at outset, but doesn't give much ability to control the rates that LEND holders are getting or to protect against risky but currently healthy loans. I'm curious what your thoughts are on this. Some governance could play a role here. For example, a minimum system wide interest rate, and a premium based on the collateral's risk (might be indexed to the mulitplier as well). A LEND holder veto, with delegation, could supplement the usual economic challenge to prevent risky-yet-healthy terms.

Possible solutions to the interest rate question:
* utilization curve + governance
* controller
* oracle (reference market rates elsewhere)

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>