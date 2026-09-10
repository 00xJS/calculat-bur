# Calculat-Bur

A real-time Bitcoin calculator webapp that converts BTC to USD at live market prices and projects future portfolio values across price targets.

**Live site: [calculat-bur.netlify.app](https://calculat-bur.netlify.app/)** — part of the [Observation Deck](https://observation-deck.netlify.app/).

The projections are arithmetic, not forecasts: each row is your BTC amount multiplied by that price target. The in-page "How this works" panel explains what the estimated market cap assumes, where the 2025 ATH figure comes from, which chart is real market data and which is arithmetic, and that custom targets are stored only in your browser.

## Layout

A dashboard rather than a stack of sections:

- A **sticky instrument rail** keeps the identity, the connection status chip, the live BTC/USD price and the refresh countdown on screen while you work further down the page.
- A **two-column workspace** (single column under 940px) puts the converter beside the price-history chart.
- A row of **stat tiles** covers 24h change, distance from the 2025 ATH, the holding's value at that ATH, and market cap / circulating supply.
- The **projections panel** carries the target chips, the bar ladder and the table.

## Features

- **Live BTC Price Ticker** — Current BTC/USD from CoinGecko with 24h change %, auto-refreshing every 60 seconds, pausing while the tab is backgrounded. A price change counts up to its new value and tints the ticker green or red for one beat
- **BTC/USD Converter** — Bidirectional, instant, satoshi-level precision. Enter the holding in **BTC, mBTC or sats** via a unit switch, or start from a dollar amount. Inputs accept `1,000` and `$1,000` as readily as `1000`, and reformat on blur
- **Quick amounts** — One-tap presets appropriate to the selected unit
- **Price History Chart** — Real BTC market data over 24H / 7D / 30D / 90D / 1Y from CoinGecko's `market_chart` endpoint, with the range's open, close and percentage change stated in text beneath it. Each range is cached in the browser (5 minutes for intraday, up to 12 hours for a year) so switching ranges does not exhaust a free, unauthenticated API
- **Future Value Projections** — A horizontal **bar ladder** and a sortable table showing holdings value at price targets ($50K–$1M), each with gain/loss vs the current price and the Bitcoin market cap that target would imply. Bars, not a line: the targets are discrete categories, and a filled line over them read as a timeline
- **Sortable table** — Any column sorts ascending/descending, by click or keyboard, with `aria-sort` announced. The header stays put while the rows scroll. Under 720px each row becomes its own labelled card rather than a horizontal-scroll trap
- **2025 ATH Target** — Pinned $126,198.07, Bitcoin's 2025 all-time high, hardcoded as a fixed reference point; it does not update if a new record is set
- **Custom Price Targets** — Add your own (rounded to whole dollars, duplicates rejected with an inline message), shown as removable chips above the table, persisted across sessions via localStorage on a best-effort basis
- **Shareable links** — *Copy share link* encodes the amount, the unit and your custom targets in the URL hash, so a view travels to another device or person — the one thing localStorage cannot do. Pasting such a link into an already-open page applies it too
- **Colour-Coded Points** — Orange (default), white (2025 ATH), magenta (custom), red/green (current price relative to ATH)
- **API Failure Fallback** — Cached pricing (refused past 24h) with a stale indicator, plain-language error messages, and a manual retry when CoinGecko is unavailable. If Chart.js fails to load, both charts are replaced by an explanation and everything else keeps working
- **Loading skeletons** — Shimmer placeholders on first paint instead of a row of `--`, which reads as broken data
- **"How This Works" Panel** — Collapsed in-page explainer covering what the projections are (and aren't), the market cap assumption, the pinned ATH, which chart is real data, and local target storage
- **Accessible by Default** — Live-region status announcements, screen-reader labels, `aria-sort` on sortable headers, chart descriptions pointing to the equivalent table or caption, a no-JavaScript notice, and full `prefers-reduced-motion` support (count-ups, tint flashes and chart animations all stand down)

## Theme

Styled with the [Observation Deck](https://observation-deck.netlify.app/) "mission control" design language — dark only (no light theme or toggle), deep navy surfaces with a warm orange accent, monospace uppercase micro-labels for data, pill-shaped status chips, and segmented controls for units and chart ranges. Nearly all colors flow through the shared token block at the top of `index.html`; Chart.js reads those same tokens at chart-build time via `getDeckTheme()`, and the history chart's gradient fill derives its rgba from them rather than hardcoding one.

## Tech Stack

- Vanilla JavaScript (no frameworks)
- Single HTML file — no build step, no package manager, nothing to install
- Chart.js 4.5.1 for data visualization (pinned to an exact version, loaded with Subresource Integrity)
- CoinGecko free API (no key required) — `simple/price` for spot, `coins/bitcoin/market_chart` for history
- Hosted on Netlify

## Getting Started

Open `index.html` in a browser or deploy to any static hosting provider.

## Disclaimer

Not financial advice. For educational and informational purposes only.
