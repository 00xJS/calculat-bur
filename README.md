# Project Calculat-Burr

A real-time Bitcoin calculator webapp that converts BTC to USD at live market prices and projects future portfolio values across price targets.

**Live site: [calculat-bur.netlify.app](https://calculat-bur.netlify.app/)** — part of the [Observation Deck](https://observation-deck.netlify.app/).

The projections are arithmetic, not forecasts: each row is your BTC amount multiplied by that price target. The in-page "How this works" panel explains what the estimated market cap assumes, where the 2025 ATH figure comes from, and that custom targets are stored only in your browser.

## Features

- **Live BTC Price Ticker** — Current BTC/USD price from CoinGecko with 24h change %, auto-refreshes every 60 seconds
- **BTC/USD Converter** — Bidirectional, instant conversion with satoshi-level precision
- **Future Value Projections** — Line chart and table showing holdings value at price targets ($50K–$1M) with gain/loss vs current price and estimated market cap per target
- **2025 ATH Target** — Pinned $126,198.07 all-time high included as a permanent reference point
- **Custom Price Targets** — Add your own targets, persisted across sessions via localStorage
- **Color-Coded Chart Points** — Orange (default), white (2025 ATH), magenta (custom), red/green (current price relative to ATH)
- **Offline Fallback** — Cached pricing with a stale indicator, plain-language error messages, and a manual retry when the API is unavailable
- **"How This Works" Panel** — Collapsed in-page explainer covering what the projections are (and aren't), the market cap assumption, the pinned ATH, and local target storage

## Theme

Styled with the [Observation Deck](https://observation-deck.netlify.app/) "mission control" design language — dark only (no light theme or toggle), deep navy surfaces with a warm orange accent, monospace uppercase micro-labels for data, and pill-shaped status chips. All colors flow through the shared token block at the top of `index.html`; Chart.js reads those same tokens at chart-build time via `getDeckTheme()`.

## Tech Stack

- Vanilla JavaScript (no frameworks)
- Chart.js for data visualization
- CoinGecko free API (no key required)
- Hosted on Netlify

## Getting Started

Open `index.html` in a browser or deploy to any static hosting provider.

## Disclaimer

Not financial advice. For educational and informational purposes only.
