# Calculat-Bur

A real-time Bitcoin calculator webapp that converts BTC to USD at live market prices and projects future portfolio values across price targets.

**Live site: [calculat-bur.netlify.app](https://calculat-bur.netlify.app/)** — part of the [Observation Deck](https://observation-deck.netlify.app/).

The projections are arithmetic, not forecasts: each row is your BTC amount multiplied by that price target. The in-page "How this works" panel explains what the estimated market cap assumes, where the 2025 ATH figure comes from, and that custom targets are stored only in your browser.

## Features

- **Live BTC Price Ticker** — Current BTC/USD price from CoinGecko with 24h change %, auto-refreshes every 60 seconds
- **BTC/USD Converter** — Bidirectional, instant conversion with satoshi-level precision
- **Future Value Projections** — Line chart and table showing holdings value at price targets ($50K–$1M) with gain/loss vs current price and estimated market cap per target
- **2025 ATH Target** — Pinned $126,198.07, Bitcoin's 2025 all-time high, hardcoded as a fixed reference point; it does not update if a new record is set
- **Custom Price Targets** — Add your own targets (rounded to whole dollars, duplicates rejected with an inline message) and remove them with the × beside the price; persisted across sessions via localStorage on a best-effort basis
- **Color-Coded Chart Points** — Orange (default), white (2025 ATH), magenta (custom), red/green (current price relative to ATH)
- **API Failure Fallback** — Cached pricing (refused past 24h) with a stale indicator, plain-language error messages, and a manual retry when CoinGecko is unavailable
- **"How This Works" Panel** — Collapsed in-page explainer covering what the projections are (and aren't), the market cap assumption, the pinned ATH, and local target storage
- **Accessible by Default** — Live-region status announcements, screen-reader labels, a chart description pointing to the equivalent table, a no-JavaScript notice, and reduced-motion support

## Theme

Styled with the [Observation Deck](https://observation-deck.netlify.app/) "mission control" design language — dark only (no light theme or toggle), deep navy surfaces with a warm orange accent, monospace uppercase micro-labels for data, and pill-shaped status chips. Nearly all colors flow through the shared token block at the top of `index.html` (a few one-off translucent overlays are inline); Chart.js reads those same tokens at chart-build time via `getDeckTheme()`.

## Tech Stack

- Vanilla JavaScript (no frameworks)
- Single HTML file — no build step, no package manager, nothing to install
- Chart.js 4.5.1 for data visualization (pinned to an exact version, loaded with Subresource Integrity)
- CoinGecko free API (no key required)
- Hosted on Netlify

## Getting Started

Open `index.html` in a browser or deploy to any static hosting provider.

## Disclaimer

Not financial advice. For educational and informational purposes only.
