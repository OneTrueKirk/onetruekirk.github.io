# Uniswap Stochastics Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This article is reviewing the submission on [modeling Uniswap positions' prices using stochastic pricing analysis](https://github.com/jfarid27/uniswap-stochastics/blob/main/Uniswap-Stochastics.pdf) by [Jalil Farid](https://twitter.com/digital_monad).

Lending and perpetuals markets have an interest in using LP positions as collateral, since it's been established that [option-like payoffs can be replicated using LP positions as debt](https://angeris.github.io/papers/rmms.pdf). As noted by Jalil, lenders do not yet have a deep handle on this. I'll warn the reader that I cannot claim to fully understand Ito's lemma or the other math in this submission, so I'll keep this review brief and look forward to the discussion.

The price of an LP position at time N depends on:
* the starting ratio of assets it holds at time 0
* price of the asset or assets it holds at time N
* the path of price between time N and 0 (which determines the trading fees)

As we can see, it is possible to robustly model the value of the position under any price movement path. Allowing leveraged exposure to arbitrary payoff structures is quite clearly desirable for lending. One of our core goals in the ECG was a sufficiently expressive framework to support an ~unlimited diversity of collateral terms. By this, I don't expect that there will be millions of low quality assets onboarded, but many distinct lending durations and risk profiles for lending against quality collateral.

We've discussed CREDIT LP pairs as collateral, but enabling them as the borrow asset opens up interesting possibilities. Market governance can't mint the pair asset out of thin air to lend, so they would have to be out of range at borrow time. A user would mint the LP position and unwrap it into CREDIT to leverage up, same as a normal borrower in terms of how they access liquidity.

Looking forward to further discussion and seeing these models compared to historical data.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>