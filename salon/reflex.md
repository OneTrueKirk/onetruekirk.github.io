# Reflex Framework Review

This is a peer review article as part of the first Credit Salon. See all the submitted articles and software projects along with my reviews here. You can comment below with your own thoughts. This article is reviewing the [Reflex smart contract framework](https://github.com/Chromaxyz/reflex), submitted by [Jack Longarzo](https://twitter.com/JackLongarzo).

## Comments

There's heated debate in the industry about upgradeable contracts, and significant developer overhead generally involved in making modifications to live contract systems. At the Ethereum Credit Guild, we have moved towards favoring immutable contracts with backwards compatibility to minimize governance risk. That said, the advantages of an upgradeable system are apparent: the user experience can be improved over time without the need for migrations. The downsides reveal themselves in events like the Compound [cETH market freeze](https://thedefiant.io/compound-ceth-frozen). Standardized frameworks for performing (and testing) upgrades seem essential to mitigate these errors.

I'm looking forward to seeing the example implementation that will be [shared here](https://github.com/chromaxyz/reflex-template). I'd also encourage the reader to take a look at some of the links in the acknowledgements, especially:

>The architecture is directly inspired by [Euler's Proxy Protocol](https://docs.euler.finance/developers/proxy-protocol) and we are thankful for their extensive documentation and novel modularization architecture.
>
>The original idea of what a Solidity framework may look like has been inspired by [Olympus DAO's Default Framework](https://github.com/fullyallocated/Default).

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>