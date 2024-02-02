# pmts
## author: William X

This is a peer review article as part of the second Credit Salon. See all the submitted articles and my reviews [here](https://onetruekirk.github.io/). You can comment below with your own thoughts. This article is reviewing an ethonline hackathon submission. See the repository [here](https://github.com/mergd/pmnts-ethonline).

Blurb from the author:

>EthOnline submission for a PWA payments app focus on mobile payments

This review will be limited in scope, since the application in question is front-end heavy and outside my area of expertise.

## The People demand a README // Passkeys are cool

Unfortunately the submission did not come with a README. However, I was able to find the associated front end repo with additional helpful content [here](https://github.com/mergd/qr-pmnts-ethonline). The Solidity is simple enough, but there are a few things worth highlighting:

* usage of XERC20 standard for smoother cross chain payments and bridging
* ability for users to rotate addresses for withdrawal or management (smart wallet functionality)
* ability for users to choose between using internal balances and external funds

The web app has some cool features, like an embedded wallet that can send transactions, and the ability to generate QR codes for crypto payments.

Passkeys (stored on a secure device like an iPhone, not in the browser) are greatly preferabe to browser or app hot wallets, and far more accessible than dedicated hardware. The combination of a passkey and a limited recovery authority seem like a promising way for more people to benefit from self custody, but avoid its pitfalls. For example, a trusted party like a bank or accountant might be authorized to rotate your passkey, but only if no transactions have occured for X days.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>