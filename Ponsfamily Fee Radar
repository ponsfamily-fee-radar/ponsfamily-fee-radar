# How to Use the Pons V2 Holder Fee Sharing Scanner to Identify Potential Earning Opportunities

The **Pons V2 Holder Fee Sharing Scanner** is a research tool designed to help users discover Pons V2 tokens with Holder Fee Sharing enabled and investigate the associated distributor data.

This guide explains how to run the scanner, interpret its output, verify distribution information, and evaluate potential opportunities while accounting for financial risks.

> **Risk warning:** This scanner identifies data worth investigating. It does not guarantee profits, predict future distributions, or calculate the exact rewards a specific wallet will receive.

## Table of Contents

1. [How Holder Fee Sharing Works](#1-how-holder-fee-sharing-works)
2. [Run the Scanner](#2-run-the-scanner)
3. [Identify Tokens Worth Investigating](#3-identify-tokens-worth-investigating)
4. [Verify Token and Distributor Data](#4-verify-token-and-distributor-data)
5. [Understand the Unallocated Amount](#5-understand-the-unallocated-amount)
6. [Estimate Your Potential Share](#6-estimate-your-potential-share)
7. [Calculate Potential Profit or Loss](#7-calculate-potential-profit-or-loss)
8. [Evaluate Liquidity and Exit Risk](#8-evaluate-liquidity-and-exit-risk)
9. [Track Historical Results](#9-track-historical-results)
10. [Important Risk Warnings](#10-important-risk-warnings)
11. [Recommended Research Workflow](#11-recommended-research-workflow)

## 1. How Holder Fee Sharing Works

When trading activity generates fees, a token's fee-sharing mechanism may allocate a portion of those fees to eligible holders, depending on the token configuration and the distributor contract's rules.

The scanner helps you identify tokens with Holder Fee Sharing enabled and review the available distributor information.

The research process is straightforward:

1. Discover potentially relevant tokens.
2. Examine their unallocated distributor amounts and distribution history.
3. Verify the underlying contract rules and current on-chain state.
4. Evaluate the potential rewards against the costs and risks of holding the token.

youtube link: https://youtu.be/PRdizMTv2Ww

**Important:** Finding a token with Holder Fee Sharing enabled does not mean that buying or holding it will be profitable.

Actual results depend on distribution rules, eligibility requirements, token price movements, liquidity, trading costs, network fees, and the amount of rewards ultimately received.

The scanner is a read-only research tool. It does not execute trades or automatically claim rewards.

## 2. Run the Scanner

Follow the project's installation instructions before starting the program.

Open a terminal and navigate to the scanner directory:

```powershell
cd C:\pons-scanner
```

Run the scanner using the project's virtual environment:

```powershell
.venv\Scripts\python.exe pons_holder_fee_scanner.py
```

Keep the terminal open while the scanner runs.

The program searches the Pons launch listing, filters for qualifying Pons V2 Holder Fee Sharing tokens, and writes its results to JSON and CSV output files.

You can open the CSV file while the scanner is running to review the latest available results, subject to the program's file-writing behavior.

**Output file:** `pons_holder_fee_sharing.csv`

## 3. Identify Tokens Worth Investigating

Open `pons_holder_fee_sharing.csv` in Excel, LibreOffice Calc, or another spreadsheet application.

Review the following fields:

| Field | Description |
|---|---|
| `name` | Token name |
| `symbol` | Token ticker |
| `token` | Token contract address |
| `holders` | Reported holder count, when available |
| `distributor_address` | Associated distributor contract address |
| `next_unallocated_quote` | Reported unallocated amount in the quote asset |
| `next_unallocated_coin` | Reported unallocated amount in the token's own asset |
| `next_round_quote_value` | Estimated quote-equivalent value of the unallocated amounts |
| `last_round_quote_value` | Quote-equivalent value recorded for the latest epoch |
| `rounds_paid` | Scanner-reported completed distribution-round count |

Field availability and calculation details depend on the scanner implementation and the data returned by its sources.

### What should you look for?

- **Unallocated amounts:** Identify tokens whose distributor balances warrant further investigation.
- **Distribution history:** Review whether previous rounds have been recorded and whether the latest epoch appears finalized.
- **Holder count:** Use this as contextual information, not as a direct measure of reward eligibility.
- **Market conditions:** Compare the apparent opportunity with the token's liquidity, trading activity, and price risk.

A larger unallocated amount does not necessarily mean a larger individual reward. Likewise, a high holder count does not automatically make a token less attractive, and a low holder count does not guarantee a better opportunity.

Use scanner fields as research indicators, not automatic buy signals.

## 4. Verify Token and Distributor Data

Before considering a purchase, open the token's Pons page and compare its information with the scanner's output.

Verify the following:

1. Confirm that the token is a Pons V2 launch.
2. Confirm that Holder Fee Sharing is enabled.
3. Verify the distributor contract address.
4. Identify the quote asset and verify its decimal precision.
5. Review the current unallocated amounts and latest epoch information.
6. Check the token's liquidity, trading activity, and available exit routes.
7. Where possible, independently verify relevant balances and contract state using an appropriate blockchain explorer or on-chain interface.

Do not assume that an older CSV record reflects the current state of the contract. Distributor balances, token prices, holder counts, and distribution states may change while the scanner is running.

Also, distinguish between raw token units and human-readable token amounts. Incorrect decimal handling can produce misleading calculations.

## 5. Understand the Unallocated Amount

The scanner's `next_round_quote_value` field estimates the quote-equivalent value of the reported unallocated quote and coin amounts.

Conceptually, the calculation is:

```text
Next Round Quote Value =
    Unallocated Quote Amount
    + (Unallocated Coin Amount × Token Price in Quote Units)
```

This calculation converts the unallocated coin amount into quote-asset units and adds it to the unallocated quote amount.

### Example

Assume a hypothetical token has the following values:

| Field | Example value |
|---|---:|
| Unallocated quote amount | 0.020 quote tokens |
| Unallocated coin amount | 100,000 token units |
| Token price in quote units | 0.0000001 quote tokens per token |
| Estimated quote-equivalent amount | 0.030 quote tokens |

The calculation is:

```text
0.020 + (100,000 × 0.0000001) = 0.030 quote tokens
```

The estimated quote-equivalent amount is therefore **0.030 quote tokens**.

These figures are illustrative only.

### What does this value actually tell you?

It estimates the combined quote-equivalent value of the reported unallocated amounts under the assumptions used in the calculation.

It does **not** establish that:

- The full amount will be distributed in the next round.
- A distribution will occur at a specific time.
- Every holder is eligible to participate.
- A particular wallet will receive a predictable share.
- The estimated amount can be realized at the displayed market price.

The distributor contract's actual rules determine how and when funds are allocated. Verify those rules before using the estimate to evaluate an opportunity.

## 6. Estimate Your Potential Share

The scanner does not calculate the exact reward that a particular wallet would receive from a future distribution.

An individual reward estimate requires a reliable understanding of the distributor's allocation mechanism.

Depending on the implementation, relevant factors may include:

- Eligible token balances.
- Balance snapshots or eligibility checkpoints.
- Distribution weighting rules.
- Minimum holding requirements.
- Claim conditions.
- Epoch finalization and rollover rules.
- Distribution timing and contract-specific restrictions.

Do not assume that every holder receives an equal share.

For example, dividing an unallocated amount by the reported holder count is **not a reliable reward estimate** unless the contract explicitly establishes equal allocation among those same eligible holders.

Before calculating an individual share, establish:

1. Which balances qualify for distribution.
2. When eligibility is determined.
3. Whether allocation is proportional to eligible balances or follows another formula.
4. Whether the reported unallocated amount is expected to be distributed.
5. Whether a claim transaction or another action is required.
6. Whether the latest epoch has been finalized.
7. Whether rollover, minimum-balance, or other restrictions apply.

If these rules cannot be verified from the contract or reliable documentation, treat the individual reward amount as unknown.

## 7. Calculate Potential Profit or Loss

A possible distribution does not automatically make a token a profitable investment.

Consider this hypothetical example:

| Item | Amount |
|---|---:|
| Initial purchase cost | 100 quote units |
| Actual reward received | 2 quote units |
| Net sale proceeds after selling costs | 95 quote units |

The net result is:

```text
Net Result =
    Actual Rewards Received
    + Net Sale Proceeds
    - Initial Purchase Cost
    - Other Costs Not Already Included
```

Using the example:

```text
95 + 2 - 100 = -3 quote units
```

The result is a **loss of 3 quote units**, despite receiving a reward.

### Evaluate the entire position

A useful framework is:

```text
Net Profit or Loss =
    Actual Rewards Received
    + Net Sale Proceeds
    - Initial Purchase Cost
    - Additional Costs
```

Make sure all values use a consistent unit and valuation basis.

Avoid counting trading fees, gas costs, or other expenses twice. If sale proceeds are already net of selling costs, do not subtract those same costs again.

For a realistic evaluation, also account for the possibility that the token's market value declines before you can exit the position.

## 8. Evaluate Liquidity and Exit Risk

Before purchasing a token, assess whether you could realistically sell your position later.

Review:

- Available liquidity.
- Recent trading volume and activity.
- Expected slippage on entry and exit.
- Price impact at your intended position size.
- The possibility of a rapid price decline.
- Whether sell transactions can execute successfully.
- Network fees and other transaction expenses.

A token may display a substantial fee-sharing amount while having insufficient liquidity for you to exit without a significant loss.

**Never treat a distributor balance as a substitute for market-liquidity analysis.**

The displayed balance is not a guarantee that you can convert the corresponding value into the quote asset at the estimated price.

## 9. Track Historical Results

Use the scanner's CSV output as a starting point for maintaining a research history.

For each token you investigate, consider recording:

- Token contract address.
- Date and time of observation.
- Reported holder count.
- Unallocated quote and coin amounts.
- Latest epoch information.
- Token price and available liquidity.
- Actual rewards received, if any.
- Purchase cost and net sale proceeds, if you trade.
- Transaction fees and other expenses.

The scanner's latest output may not preserve every historical observation. If historical comparisons are important, save dated copies of the output files or maintain a separate historical database.

Evaluate your approach using actual realized results rather than the size of unallocated balances alone.

A historical record can help distinguish between apparent opportunities and positions that actually generated a positive net result.

## 10. Important Risk Warnings

Read these warnings before using scanner results to make financial decisions.

**No guaranteed income**

Holder Fee Sharing does not guarantee future fee generation, a future distribution, or payment to a particular holder.

**Token price risk**

A token's market price can fall substantially or become effectively worthless. Losses from price movements may exceed any rewards received.

**Liquidity risk**

You may be unable to sell at the displayed price. Low liquidity and high slippage can materially reduce your proceeds.

**Distribution risk**

Unallocated balances, completed epochs, and historical distributions do not guarantee future payments. Contract rules may impose eligibility requirements, rollover conditions, or other restrictions.

**Data risk**

Pons APIs, blockchain RPC endpoints, and blockchain explorers may return delayed, incomplete, or unavailable data. API behavior and response formats may also change. A scanner result is an observation, not a guarantee of the contract's current state.

**Holder-count limitations**

A reported holder count may be unavailable or may not reflect the number of participants eligible for a particular distribution.

**Reward-estimation limitations**

The scanner does not currently determine the exact amount a specific wallet would receive from a future distribution.

**No automatic trading or claiming**

The scanner is a read-only research tool. It does not buy tokens, sell tokens, claim rewards, or guarantee that a transaction can execute successfully.

**Independent verification**

Verify token addresses, distributor contracts, allocation rules, market conditions, and relevant on-chain data before making financial decisions.

**Personal responsibility**

You are responsible for your own trading decisions. Never commit funds you cannot afford to lose.

## 11. Recommended Research Workflow

Use this checklist for each newly discovered token:

- [ ] Find the token in the scanner's output.
- [ ] Verify the token and distributor contract addresses.
- [ ] Confirm that Holder Fee Sharing is active.
- [ ] Review the unallocated amounts and latest epoch information.
- [ ] Investigate the actual allocation and claim rules.
- [ ] Check liquidity, trading activity, slippage, and price risk.
- [ ] Estimate potential rewards only when the required information is available.
- [ ] Compare potential rewards with acquisition costs, exit costs, and downside risk.
- [ ] Decide independently whether the risk is acceptable.
- [ ] Record actual rewards, proceeds, and expenses if you choose to trade.

---

## Final Reminder

The Pons V2 Holder Fee Sharing Scanner is designed to help you discover and investigate relevant on-chain data more efficiently.

It does not identify guaranteed profits, predict future payouts, or replace independent contract and market analysis.

**A large unallocated balance is a reason to investigate, not a reason to buy.**

Always verify the underlying data, understand the distribution rules, evaluate the full cost of a position, and make your own informed decision.
