# Market Pulse — trader dashboard

Real-time economic indicators and market-valuation gauges for traders and
investors. No API keys — data from FRED, multpl.com, and Yahoo Finance.

## Run

```bash
pip install -r requirements.txt
streamlit run app.py
```

## What's inside

- **Regime strip** — six at-a-glance pills: valuation (CAPE percentile),
  yield-curve shape, credit stress, VIX fear, labor (Sahm rule), inflation
  vs the Fed's 2% target.
- **💰 Valuation tab** — Shiller CAPE (live history + percentile), Buffett
  indicator (official annual series + live estimate with disclosed method),
  excess CAPE yield, trailing P/E, price/sales, dividend yield.
- **🏭 Economy tab** — GDP, industrial production, retail sales; unemployment,
  payrolls, jobless claims, JOLTS, wage growth; CPI headline/core, core PCE,
  5-yr breakevens; 2-yr/10-yr yields, 2s10s curve, real yields; Michigan
  sentiment, Case-Shiller, housing starts, mortgage rates.
- **📈 Markets tab** — S&P 500, VIX, 10-yr yield, equal-vs-cap-weight breadth
  (RSP/SPY), HY/IG credit spreads, dollar, gold, copper, oil, bitcoin.

## Notes

- FRED's public CSV endpoint is rate-limited; series are fetched politely
  (3 workers + backoff) and cached for 6 hours, Yahoo data for 1 hour.
- Any series that fails to load shows "data unavailable" instead of breaking
  the app.
- Valuation gauges predict long-horizon returns, not market timing.
  Research tooling, not investment advice.
