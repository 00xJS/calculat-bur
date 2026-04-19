# Project Calculat-Burr

A real-time Bitcoin calculator webapp that converts BTC to USD at live market prices, projects future portfolio values across price targets, and compares Bitcoin against gold.

## Features

- **Live BTC Price Ticker** — Current BTC/USD price from CoinGecko with 24h change %, auto-refreshes every 60 seconds
- **BTC/USD Converter** — Bidirectional, instant conversion with satoshi-level precision
- **Future Value Projections** — Line chart and table showing holdings value at price targets ($50K–$1M) with gain/loss vs current price and estimated market cap per target
- **2025 ATH Target** — Pinned $126,198.07 all-time high included as a permanent reference point
- **Custom Price Targets** — Add your own targets, persisted across sessions via localStorage
- **Color-Coded Chart Points** — Orange (default), black (2025 ATH), blue (custom), red/green (current price relative to ATH)
- **Gold vs Bitcoin** — 8 live stat cards comparing gold and BTC including gold price, market caps, Gold/BTC ratio, BTC at gold parity, gold oz per 1 BTC, and more
- **Offline Fallback** — Cached pricing with stale indicator when API is unavailable

## Tech Stack

- Vanilla JavaScript (no frameworks)
- Chart.js for data visualization
- CoinGecko free API (no key required)
- Hosted on Netlify

## Getting Started

Open `index.html` in a browser or deploy to any static hosting provider.

## Disclaimer

Not financial advice. For educational and informational purposes only.
