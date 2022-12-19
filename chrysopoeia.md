# Chrysopoeia
> on the folly of trying to turn lead into gold

![img](640px-Midas_gold2_wiki_580.jpeg)

I've had some arguments today about whether it is possible to safely back a derivative with endogenous collateral. My answer and that of history is a resounding NO. This is a quick treatment but hopefully the elaboration of the argument will help to persuade.

Some examples in this category are sUSD/SNX, UST/LUNA, SPOT/AMPL, and BEAN/pods, with widely divergent implementations but the same fatal conceit. Each system believes it can create something from nothing, and attempts to induce users to accept derivatives that fundamentally have no underlying value in exchange for real assets. It's no different in the "real world", where the Argentine peso now trades severely under "peg" against the dollar due to unbalanced trade and the bad credit of its government.

Mechanisms and in brief:

sUSD and other Synthetix synths: mint against overcollateralized SNX positions, whose value is derived from a mix of current usage and expectations of future growth (moreso the latter). While nominally overcollateralized, it's absurd to think that the entire supply could be redeemed at par, as surge in demand to redeem synths and sUSD would put downward pressure on SNX price.

UST: mint a dollar pegged derivative against LUNA, an L1 whose primary use case is using UST. LUNA emissions were used to subsidize yields on UST lockups in a lending market. When a large demand to sell UST comes, it puts pressure on LUNA price, breaking the ability to backstop the UST peg.

Bean: Offer impossible yield promises to induce users to lock up their BEAN as pods and push the price to target. The only possible source of yield for pods is demand for BEAN, yet pods are used to subsidize demand for BEAN. Either a drop in demand for BEAN or pods can thus cause a drop in the other, and only if the system perpetualy grows can the pods get paid.

SPOT: Backed by a mixture of AMPL and AMPL derivatives, which themselves have no inherent value as AMPL has no revenue or notable use case. If SPOT grew to a large size, it would thus be the main driver of AMPL demand. Advertised as a store of value, but with endogenous collateral, any large wave of redemption and sale would depress the price of AMPL and any other backing derivative.

Our position:

1. There is no reason to believe that endogenous collateral systems can be effective either in theory or history. I challenge the reader to find even one example in TradFi or DeFi that worked at scale and over time.

2. Claims that such "experiments" deserve to be tried are an excuse for fraudsters and directly lead to loss of innocent user funds. We have ample historical and theoretical grounds to reject such attempts outright.

Why can't endogenous collateral work? The best way I can put it is that endogenously collateralized systems don't need any particular reason to fail. If a loss of confidence occurs in the system **for any reason**, users will be unable to exit at the value they anticipate and a bank run dynamic can ensue. "It might work" is an inadequate reasoning structure when real money is at stake. What's key is that there are many situations in which a crisis of confidence may occur, and no reason to believe these systems can resist the stress of the collapse of the endogenous collateral's value, regardless of the reason for that decline.

This is why the idea that "Terra collapsed because it was attacked" is bogus. Terra was doomed to collapse the moment its users realized they had exchanged their real money and savings for unbacked monopoly cash, and a stampede for the gates ensued. 

It doesn't matter what kind of fancy math you use, there's no way to magically turn endogenous into non-endogenous collateral. In the case of Ampleforth's SPOT, a tranching system of AMPL is used in an attempt to provide stability. If the market cap of AMPL was to decline by 90%, however, no amount of tranching will save the value of its derivative. Given that this scenario could occur for any one of a number of reasons (failure to achieve adoption, exploit, external shock, economic attack), it's absurd to say such an instrumnt could be a reliable store of value.

I'll leave you with a few warning signs to watch out for with these kind of products:
* attempts to move goalposts with alternative or non-standard definitions and made-up terminology. A synthetic is a synthetic, it doesn't matter whether you call it an ETF, a stablecoin, a free floating reserve currency, of a unit of account. You still can't keep stability at any peg, in any range, or relative to anything using purely endogenous collateral. It has never been done and never will be.
* primacy of decentralization concerns used to suppress worry about lack of backing. Sure, you might not like USDC, but you won't make it go away by closing your eyes.
* overly complex (obscurantist) mathematical structures. If it doesn't OBVIOUSLY add up how the price mechanism works, it's more likely that something is deeply wrong than that you are missing something.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>