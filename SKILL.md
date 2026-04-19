---
name: politician-trades
description: Use when Raymond asks about politician/congressional stock trades, invokes /politician-trades, or says "what did Pelosi buy". Returns the most recent STOCK Act-disclosed trades for the named politician as a table. Pelosi is the default.
---

# politician-trades

Fetch recent disclosed stock trades for US politicians via Capitol Trades.

## Triggers

- `/politician-trades` → default: Nancy Pelosi
- `/politician-trades [name]` → e.g. `/politician-trades Tuberville`
- "what did [name] buy/sell", "any new congress trades", "track [name]'s trades"

## How to run

1. Resolve bioguide ID from the table below. If not listed, WebSearch "[name] bioguide id" and proceed.
2. `WebFetch https://www.capitoltrades.com/politicians/<BIOGUIDE_ID>` — ask it to extract the 10 most recent trades with: traded date, ticker, issuer, buy/sell, size range, published date.
3. Render as a markdown table. Columns: `Traded | Ticker | Side | Size | Published`.
4. No side effects — don't write files, don't auto-add tickers to watchlists.

## Known politicians

| Name | Bioguide |
|---|---|
| Nancy Pelosi (House, D) | P000197 |

Extend inline as needed. Same URL pattern covers House + Senate.

## Example (verified 2026-01-26)

`/politician-trades Pelosi` →

| Traded | Ticker | Side | Size |
|---|---|---|---|
| 2026-01-16 | AB | Buy | $1M–$5M |
| 2026-01-16 | GOOGL | Buy | $500K–$1M |
| 2026-01-16 | AMZN | Buy | $500K–$1M |
| 2025-12-30 | AAPL | Sell | $5M–$25M |
| 2025-12-24 | AAPL | Sell | $5M–$25M |

Theme: rebalancing out of AAPL/NVDA/AMZN, building AB + long-dated GOOGL calls.
