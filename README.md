# Project Calculat-Burr

A real-time Bitcoin calculator webapp that converts BTC to USD at live market prices and projects future portfolio values across custom price targets.

## Features

- **Live Price Ticker** — Current BTC/USD price from CoinGecko with 24h change %, auto-refreshes every 60 seconds
- **BTC/USD Converter** — Bidirectional, instant conversion with satoshi-level precision
- **Future Value Projections** — Table and bar chart showing holdings value at price targets ($50K–$1M) with gain/loss vs current price
- **Custom Price Targets** — Add your own targets, persisted across sessions via localStorage
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
