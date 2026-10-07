# Leader Rotation Lab

Monthly leader-rotation backtester. Open `index.html` in any browser — no install, no server.

## The rule
1. On the 1st of each month, rank every stock by its **12-month return** (3 or 6 months also available).
2. Keep only stocks **above their 10-month average**.
3. Buy the **top N** equally (default 10), max **3 per sector** (adjustable), one share class per company.
4. **Never sell.** Every monthly basket is held to today.
5. SPY and QQQ are bought with the same dollars on the same dates as benchmarks.

## What it shows
- **This month's buy list** with sector, price and dollar amounts
- **Concentration Lab** — 3 / 5 / 10 / 20 stocks × no cap / max 3 / max 2 per sector
- **Test window** (12–120 months or all history): value vs QQQ, SPY and 30 random-pick runs
- **Monthly cohorts**, **where the gains came from**, **full-history torture test** (rolling 36-month windows, regimes, without the best 10 names)

## How returns are calculated
- **Total return** = value today of all monthly purchases ÷ total dollars invested − 1
- **Per year** = money-weighted annual return (IRR) on the monthly deposits
- No taxes or trading costs

## Updating the data
Add the new month's prices to `data/MY_OWN.csv` (rows = dates, columns = tickers, include SPY and QQQ), then drop the file onto the page.
A last row dated mid-month is treated as "today's" price; broken prices (`#FIELD!`, 0.01, etc.) are replaced with the prior month and flagged.
The price data is also built into `index.html`, so the page works on its own.

## Files
| File | What |
|---|---|
| `index.html` | The whole app (code + built-in data) |
| `data/MY_OWN.csv` | Monthly price history, Nov 2000 → Oct 2026 |
