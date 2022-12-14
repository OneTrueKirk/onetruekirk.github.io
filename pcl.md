# Protocol for Callable Loans

How good anything is as collateral cannot be known with certainty. What can be sold today for a high price may find no buyers at all tomorrow. Handling assets as collateral thus requires constant observation, evaluation, and adjustment. It is also competitive. If we both need to liquidate the same asset, and I act first, I am likely to receive a better price.

In this context, it is clear that existing monolithic lending markets like Compound and Aave are flawed. They rely on oracle feeds that are vulnerable to market manipulation attacks and frontrunning. Once the amount of an asset borrowable in DeFi exceeds a certain threshold vs its real market depth, the lending markets become vulnerable to attack. We’ve seen this recently with long tail assets, but it could happen with anything, even BTC or ETH, once sufficient borrowable liquidity becomes available. In the event bad debt occurs, a bank run dynamic ensues, where less sophisticated lenders are likely to take a total loss while sophisticated lenders escape losses. Any automated price reporting mechanism for collateral valuation is subject to these risks. 

By admitting only a single (or a narrow set of) lending terms in a given market, lenders are unable to meaningfully risk-differentiate when giving loans. Lenders are unable to call loans that have become risky. Raising rates is insufficient to produce liquidity on demand in extreme market scenarios. Like passive Uniswap LPs, lenders are at the mercy of sophisticated outside actors. The existing implementations put lenders on the back foot vs sophisticated borrowers. Beneficial competition between lenders (ie, different rate and risk opinions) cannot occur, but malignant competition (bank run risk in event of bad debt) is a looming threat. What’s more, they are at risk due to potentially unwise decisions or software errors by pool operators.

The alternative I’m brainstorming is a “protocol for callable loans” (PCL). The PCL should be governance free and oracle free, such that lenders are entirely in control with no counterparty risk besides their exposure to the borrower’s collateral position.

To accomplish this, we must give up on the idea of a passive lending pool and embrace the understanding that lenders and borrowers are sophisticated, self-interested, and at times adversarial actors. Users may be either protocols, individuals, or entities, the underlying PCL should be as neutral and composable as possible.

Below is an incomplete and actively-evolving sketch of how I could see this working.

# Specification

A Loan has:
* Collateral token
* Borrow token
* Initial token ratio
* Start time
* Interest rate

A Lender is either matched or unmatched. Unmatched Lenders can set the interest rate they expect on loans and the ratio of collateral tokens: borrowed tokens they require, or are free to withdraw at any time. A Borrower initiates a Borrow by posting the necessary collateral and matching with one or more Lenders in a set of Loans. Routing can be done offchain, the Borrower will call in with a set of Lender positions to match with. The price to repay the loan is based on the initial token ratio, the interest rate, and the time elapsed since the start time.

Matched Lenders can only withdraw atomically if there are enough Unmatched Lenders to take over their loans at equal or lower rates and collateral ratio. When there is no liquidity available to take over the loans and allow them to withdraw, Matched Lenders can “call” loans by paying a fee (the liquidation fee). This triggers an auction of all or part of the collateral backing the loan(s) of the borrower(s) they are matched with. The Borrower will have “right of first refusal” on the auction to repay their loan in full minus the liquidation fee. If the Borrower does not exercise this right, a normal liquidation auction will proceed, and the Lender will recoup their principal along with the liquidation fee if the proceeds are sufficient, or take a partial loss if they waited too long and the position became undercollateralized.

The duration of the auction and how long the borrower has to act are important parameters. An MVP system might standardize these, but these parameters could be set by the Lender as part of the Loan variables.

From a Borrower’s perspective, their loan is of indefinite duration with fixed rate, and they will receive a small compensation if it is recalled before they choose to repay.

This does not require any oracle. It does require both Lenders and Borrowers to be active participants, at the minimum running keepers. The UX is hostile to casual participants, but with the right tooling and abstraction could be improved.

Volt Protocol could use this system by allowing VCON holders to act as Lenders, allocating PCV in loans against assets like ETH staking derivatives and tokenized yield bearing real world assets. It could also be used independently by entities seeking credit against arbitrary tokenized assets.

# Usage Example

I define a new lending pool, USDC-ETH, whose liquidation fee is 0.1%.

I set my lending rate at 1% borrow rate and a minimum ratio of 1 ETH collateral for every $1k borrowed (effectively a 120% CR at current prices), and deposit 100k USDC into the pool.

A user deposits 100 ETH into the pool as collateral and borrows my full 100k USDC, and starts paying 1%.

After a while, the price of ETH declines such that the borrower position is at only 110% CR. This makes me uneasy, so I pay 0.1% ($100) to call the loan. As the position is still solvent, the borrower is able to repay in full and awarded $100 for the trouble, likely paying between $50 and $150 to unwind their position depending on how they execute, or a liquidator will do the same on their behalf if they are negligent.

Borrowers may prefer pools with higher liquidation fees (more costly for lenders to call the loan), while lenders may prefer a lower cost to call. Like different Uniswap fee tiers, it is non obvious what the preferences of market actors are a priori and useful to have an expressive system.

# Summary

Current lending pools impose the burden of liquidation fees on borrowers and use dynamic rates to manage liquidity, yet do not allow lenders to directly “call” loans and access liquidity on demand. In other words, loans have infinite duration unless they drop into liquidatable range.

The system described here imposes the burden of liquidation fees on lenders and fixes rates at borrow time, yet allows direct calling of loans (guaranteed time-to-withdraw for the lenders, instead of uncertain wait times or bank runs in a liquidity crunch). In other words, loan duration is determinable by the lender, but they must pay the cost of closing the loan.
