<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6FD3E90TCT"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6FD3E90TCT');
</script>
# Governance Roundup Dec 5

This post is the second in a series of public checkpoints of governance activity in all protocols where Volt Protocol has made PCV deposits.

Read past issues here:
[November 14](gov14nov.md)

![img](IMG_0724.png)
> a different kind of yield farming

## Compound v2

Borrow caps were either imposed or increased on ten Compound assets in [CIP-135](https://compound.finance/governance/proposals/135):
* WBTC
* BAT
* UNI
* COMP
* LINK
* SUSHI
* ZRX
* AAVE
* YFI
* MKR

A sensible precaution in light of recent [market manipulation](https://blockworks.co/news/mango-markets-exploit-plot-revealed) [attempts](https://thedefiant.io/crv-trade-aave-bad-debt), some more successful than others.

As stated [elsewhere](https://www.comp.xyz/t/v2-market-hardening-and-collateral-adjustments/3783), I believe that Compound v2 and Aave v2 should actively offboard assets whose market depth is small compared to the borrowable stablecoin and ETH supplies in their respective markets. Per asset supply limits and other safeguards as found in the v3 markets can isolate risk to acceptable bounds, making them better suited for these assets.

There's an [interesting discussion](https://www.comp.xyz/t/compound-risk-council/3823/3) in the Compound forum suggesting more granular governance mechanisms to respond to risk, such as a risk council multisig authorized to make certain parameter adjustments but not code changes etc. I think it's a great idea and will lead to reduced risk for lenders.

## Morpho

There's an [ongoing discussion](https://forum.morpho.xyz/t/mip-add-granular-pausing-and-asset-deprecation/213/4) about adding more granular market pausing based on the lessons drawn from recent experience. I'm in favor of the direction suggested by Morpho Labs, and added a note with a suggestion.

I cast my [first Morpho Snapshot vote](https://snapshot.org/#/morpho.eth/proposal/0x816e4971cd3919bc8df7ad0892ead985f8eba8d72a7644a6b5a022847b123059) in favor of allowing Sense contracts and Morpho's vaults to transfer MORPHO tokens, allowing users of those applications to claim and vote. The Sense market speculating on the value of MORPHO tokens is interesting and worth a look. There are buyers for Morpho-Aave-DAI yield at 4% fixed for seven months, speculating on the MORPHO reward stream. If you hold MORPHO, you can delegate to me at onetruekirk.eth. Read my [delegate platform](morpho_delegate.md) here.

## MakerDAO

On a related note, MakerDAO has approved [reenabling its Compound v2 Direct Deposit Module](https://vote.makerdao.com/executive/template-executive-vote-compound-d3m-onboarding-activating-stablecoin-liquidations-oracle-feed-whitelisting-starknet-relay-upgrade-and-mkr-vesting-december-2-2022#proposal-detail), setting a target DAI borrow rate at 2%. While its initial debt ceiling is only 5m DAI, we can assume this will increase in the future.

Across the board, MakerDAO is tightening up and derisking by lowering debt ceilings on problem assets.

>A recent proposal tightened MANA-A parameters to address extremely high observed risk levels. Liquidity and market risk remains elevated, and possible DCG related holdings also indicate potentially higher risk levels. For the time being it is recommended to reduce the debt ceiling to 0. In the future if risk conditions improve the debt ceiling could be reinstated, or alternatively the vault could be offboarded at the discretion of Maker governance if it no longer fits within overall protocol strategy.

You love to see it.

<script src="https://utteranc.es/client.js"
        repo="OneTrueKirk/onetruekirk.github.io"
        issue-term="pathname"
        label="comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>