# Forex Command

A standalone GitHub Pages forex dashboard for EUR/USD, USD/JPY and USD/CAD.

## Features
- Session status clocks for Tokyo, London and New York (New York time).
- Previous completed daily candle high, low and midpoint.
- Multi-timeframe EMA trend assessment (1D, 4H, 1H, 15M, 5M).
- Conditional setup references based on 1H/15M agreement and 5M volatility.
- Economic calendar link and pre-news caution reminder.
- PWA install support.

## Deploy
1. Create a new GitHub repository named `forex-command`.
2. Upload all files in this folder to the repository root.
3. In Settings > Pages, deploy from the `main` branch and `/ (root)`.
4. Open the published URL.

## Market data
This version uses the Twelve Data time-series endpoint. Create an API key at https://twelvedata.com/ and enter it in the dashboard. The key is saved in this browser's localStorage. This is suitable for a private personal prototype, but it is not secure for a public website because browser users can inspect requests and local storage. For a production/public deployment, proxy requests through a server-side service and store the key in its secrets manager.

The app requests five intervals for each of three symbols. Check the API plan's FX coverage, interval availability, credit limits and delayed/real-time status. If a request fails, the dashboard reports an error. It does not fabricate quotes.

## Important limitations
- Session clock hours are indicative standard session windows in New York time; holidays and broker-specific liquidity conditions are not modeled.
- Trend classification is a simple EMA20/EMA50 and recent-slope heuristic, not a predictive model.
- Setup entry/stop/target values are volatility-based references, not broker orders or guaranteed levels. Confirm price action, spread, execution conditions and risk independently.
- Economic calendar is linked externally and not embedded. Calendar feed integration can be added separately with a suitable provider.
- Data refresh is manual; browser auto-refresh is not enabled to avoid exhausting API quotas.
