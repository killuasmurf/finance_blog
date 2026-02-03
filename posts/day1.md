# Day 1: ETFs vs. Mutual Funds
**Date:** Feb 03, 2026

## The Concept
As a student, I used to think "investing" was just one big function: `invest(money) -> profit`.
Today I learned that the *implementation* of that function matters.

### 1. The Execution Model
* **Mutual Funds (Batch Processed):** Trading Time is **Once a day**. You buy/sell at the end of the day. You don't know the exact price until the day is over. You pay the Net Asset Value (NAV).
* **ETFs (Real-Time):** They trade like stocks. You can buy/sell instantly, and price move second-by-second.

### 2. The Cost Analysis
The biggest difference is the **Expense Ratio** (Fees).
* My Mutual Funds: ~1.5%, generally worse in long term.
* VOO ETF: ~0.03%

**The Formula:**
The impact of fees compounds over time using the standard interest formula:

`Final Amount = Principal * (1 + Return - Fees)^Years`

If I invest $10,000 for 30 years at 8% growth:
* **With ETF (0.03% fee):** Result is ~$100,000
* **With Fund (1.50% fee):** Result is ~$66,000

*That is a $34,000 difference just from a small percentage change!*

## Python Proof
Here is the script I used to calculate the difference:

```python
principal = 10000
rate = 0.08
years = 30

# Calculate specific impact
val_etf = principal * (1 + rate - 0.0003)**years
val_fund = principal * (1 + rate - 0.015)**years

print(f"ETF Result: ${val_etf:.2f}")
print(f"Fund Result: ${val_fund:.2f}")
print(f"Difference: ${val_etf - val_fund:.2f}")

