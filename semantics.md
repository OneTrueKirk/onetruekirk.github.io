# Semantics

I've been having a few discussions recently about the nature of money creation, centered around the question "can commercial banks create money (and cause inflation)?"

My interlocutors say yes they can. For example, [Sebastien Derivaux concludes](https://cryptobanking.network/how-money-work/)
> As we have seen, it is commercial banks that are creating money. Reality is obviously more complex as the government can be more active than in our short presentation. Nevertheless, a balance sheet view is always useful to understand what is really happening.
>
>The direct conclusion is that if stablecoins are seen as money (usable for payments) AND the stablecoin issuers aren’t backed only by money (money base or money supply) THEN there is monetary creation.

I disagree and must insist that commercial bank loan issuance, or stablecoin supply expansion, does not and cannot cause USD inflation, only perhaps be the result of it, or the mechanism by which it acts.

Several people have dismissed this as a semantic difference in conversation. For a definition of semantics, Merriam-Webster gives us `the study of meaning` as the short definition of semantics, and `the historical and psychological study and the classification of changes in the signification of words or forms viewed as factors in linguistic development` for the more verbose.

To me, the actual locus of money creation is much more than an argument over labels. It is at the crux of discussion of whether there *ought* to be a central bank or other forms of central regulatory controls on the banking system. After all, if banks can create money, so too can they abuse this privilege. The fact that banks **cannot** issue more in loans than they can finance through a combination of customer deposits and credit from the central bank or other banks is therefore deserving of public emphasis. Base money creation occurs only in the central bank.

# Gold Standard as an Illustration

Using the model of a gold standard clarifies things. For our system, we will define one unit of currency, which can be a Mark instead of a Dollar, as equal to 1 gram of gold of an agreed purity.

In this system, any bank might be free to issue paper currency redeemable for its face value in gold. Such currency would be marked and associated with the issuing bank. To keep things closer to our own society, we'll instead say that only the Royal Mint may issue or redeem paper currency, but it will do so at cost at the request of any banks or persons with larger than a minimum redemption quantity.

Banks issue loans denominated in gold marks, but payable in paper currency, interbank transfer, gold, or possibly even foreign currencies.

If a bank issues a new loan, a borrower might draw upon funds to make a purchase, which are then placed into a second bank by the receiver. Most likely, instead of the borrower physically withdrawing gold, they will make payment with a check or note. The receiving bank, however, has [a strong incentive](https://www.bloomberg.com/news/articles/2022-09-05/binance-says-it-s-converting-users-usdc-into-its-own-stablecoin) to get assets off the books of its rivals so it can start earning interest on them.

This may proceed bilaterally or, more likely, through a clearinghouse. The significance of this is that a bank cannot extend loans greater than the credit available to it by any means, or it will soon face margin call. The fact that clearinghouse members have a certain amount of credit available to them or settle at fixed intervals does not mean banks have the freedom to alter the overall money supply or ratio between hard money and bank deposits.

Nowhere in this process does the need arise for external controls to prevent inflation due to excess lending. These controls are endemic in the response of the market. Base money creation occurs only with the mining of new gold or the monetization of nonmonetary stores (ie, jewelry -> bank reserves of gold).

# Read Selgin Please

Selgin's Theory of Free Banking crystallized my understanding of these systems. [Read it in full here](https://oll.libertyfund.org/title/white-the-theory-of-free-banking-money-supply-under-competitive-note-issue) (seriously). One of the most important lessons I drew from it is that a free banking system can exist even with a monopoly bank of issue, and does not benefit from regulatory control.

A fiat system can approximate or even outperform the gold standard depending on how it is governed. What is required is not necessarily abandoning the USD, but making it as predictable and credibly neutral as possible. Some argue for a "zero inflation" standard, while the orthodoxy is a low single digit inflation target. There is good reason to think that long run, [the system should be deflationary due to productivity increases](https://iea.org.uk/publications/research/less-zero). Even a gold standard did not have "perfect" supply properties, whatever that means, as there were occasional shocks from discoveries of new large gold deposits. Stability and predictability is likely more important than any specific rate target.

Regardless of the properties of the base money, the nature of a healthy free banking system on top of it is basically similar. Many large banks survived a switch from the gold standard to the modern fiat regime in comfort, and would just as easily switch to offering ETH-denominated loans if this were what the market desired. The prevailing interest rates at different maturities will reflect the expected and historical behavior of the base money supply.

# What does this mean for stablecoins?

1. Stablecoins are not a source of structural risk for the USD financial system, we should beware and push back against regulators who cry wolf, and be cautious about accuracy in language of where money is really created. In reality, a small group controlling a Central Bank Digital Currency are far more likely to mismanage it than a large network of stablecoin issuers are to simultaneously fail.
2. Stablecoins are similar to bank deposits or private banknotes under a free issuance regime. Neither demands regulation to function in a healthy way, but we should look to banking history in the design of stablecoin systems. Stablecoin protocols should pay close attention to their cost of capital and underlying maturities. Their ability to seek yield is stricly limited by their access to credit or deposits. TVL that is being incentivized at above-market rates is fool's gold and a recipe for future runs.

I'll leave you with Bagehot.

>I shall have failed in my purpose if I have not proved that the system of entrusting all our reserve to a single board, like that of the Bank directors, is very anomalous; that it is very dangerous; that its bad consequences, though much felt, have not been fully seen; that they have been obscured by traditional arguments and hidden in the dust of ancient controversies.
>
>But it will be said—What would be better? What other system could there be? We are so accustomed to a system of banking, dependent for its cardinal function on a single bank, that we can hardly conceive of any other. But the natural system—that which would have sprung up if Government had let banking alone—is that of many banks of equal or not altogether unequal size. In all other trades competition brings the traders to a rough approximate equality. In cotton spinning, no single firm far and permanently outstrips the others. There is no tendency to a monarchy in the cotton world; nor, where banking has been left free, is there any tendency to a monarchy in banking either.

![](bagehot.jpeg)

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>