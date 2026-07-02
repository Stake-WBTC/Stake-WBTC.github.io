# Codex task: premium 2026 redesign of the Stake WBTC landing page (LIGHT) + a clean TradingView chart section + WBTC authorities

Rebuild this static one-page site IN PLACE (your -C workdir): overwrite `index.html` + `style.css`, keep
every other file. No frameworks, no build, no external JS libraries (EXCEPTION: the official TradingView
embed widget script, see CHART). Premium, modern, 2026 -- NOT dry, NOT chunky.

IMAGES ARE FROZEN (local): never create, overwrite, download, replace, rename, or delete any LOCAL image
(`favicon.png`, `eth.png`, `sol.png`, `usdt.png`, `stakecrypto.png`, `og-cover.png`, any local
`*.png`/`*.svg`/`*.ico`). Use ONLY the local images already in the folder, byte-unchanged. Keep
`<link rel="icon">` and the topbar brand `<img>` on the existing `favicon.png` (no inline `<svg>`, no data-URI).
NOTE: there is NO local WBTC/BTC icon -- render WBTC as a clean styled TEXT chip (a small orange dot +
`WBTC`); do NOT fabricate or download a WBTC icon. EXTERNAL images allowed ONLY for the authority-source
logos (favicon service) and the TradingView widget. No new LOCAL files.

PRESERVE from the current `index.html` (read it first): the exact keyword `Stake WBTC` (as `<h1>` and in
`<title>`), the existing value sentence (deck `<p>` = `<meta description>`, word-for-word, light polish
only), the `<link rel=canonical>`, the money CTA target href.

## IMPORTANT -- THIS PAGE SCROLLS (not a one-screen lock)
The HERO is a strong premium FIRST screen. The page then SCROLLS DOWN to: (1) a clean TradingView WBTC chart
section, (2) the 5 WBTC authority links BELOW the chart, (3) the footer. Normal document flow -- do NOT set
`overflow:hidden`/`height:100vh` lock on the body. `overflow-x:hidden` only. No horizontal overflow anywhere.

## THEME: LIGHT premium 2026 (WBTC = Bitcoin)
- Clean LIGHT base; ONE accent = Bitcoin orange (~`#F7931A`; confirm via `favicon.png`). Soft white cards,
  GENEROUS rounded corners (~16-22px), gentle soft shadows, hairline neutral borders, airy whitespace. ONE
  accent, no rainbow. `<meta theme-color>` = the light base. Quiet premium motion; respect `prefers-reduced-motion`.

## SEO spine (LOCKED)
- `<title>` = `Stake WBTC &mdash; <short hook>` (em-dash, keyword first, <=60 chars, no weak suffix).
- Exactly one `<h1>` = `Stake WBTC`. NO `<h2>`. Deck `<p>` wraps `<strong>Stake WBTC</strong>` and equals
  `<meta description>` word-for-word. Schema `@graph` = WebSite + WebApplication + Organization, truthful, no
  FAQ/HowTo. SEO text in source HTML.

## BUTTON STYLE (2026-modern, refined)
Both CTAs: hero ~50px / card ~48px, radius ~12-13px, font-weight ~600-650, slight negative letter-spacing.
Clean accent fill + subtle top inner highlight + faint 1px ring + a TIGHT low accent-tinted shadow (NOT a big
glow). A small arrow (`&rsaquo;`) that nudges ~3px right on hover with a gentle 1px lift.

## Section 1 -- HERO (first screen, split)
- **Topbar:** brand mark (`favicon.png`) + `Stake WBTC` wordmark LEFT; flexible spacer; THREE WBTC
  super-authority links on the RIGHT (replace the old generic ones), plain text,
  `target="_blank" rel="nofollow noopener noreferrer"`:
  - WBTC -> https://www.wbtc.network/
  - BitGo -> https://www.bitgo.com/
  - Etherscan -> https://etherscan.io/token/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599
  No topbar button.
- **Left:** `<h1>Stake WBTC</h1>` (RENDER ~80px on desktop, e.g. `clamp(2.9rem,5.6vw,5.1rem)`, never under 64px)
  -> deck `<p>` (keyword in `<strong>`) -> THREE qualitative chips (e.g. `WBTC staking`, `Non-custodial`,
  `Earn on Bitcoin`) -> ONE primary CTA `Enter App`. NO `<h2>`.
- **Right (the star):** a RICH light STAKE-CONSOLE card (this is STAKING, not a swap): chrome + a small
  selector pill + a pulsing `Preview` pill; a WBTC asset panel -- WBTC shown as a clean styled TEXT chip
  (small orange dot + `WBTC`) -- flowing to a "Staked / Earning" state (a second panel or a clean badge);
  a faint number-free hint like `Rewards in app` / `APR shown in app` (NO fabricated APY/numbers); the
  `Start Staking` CTA. Non-interactive preview. No wallet connect, no fake amounts/APY.

## Section 2 -- TradingView CHART (scroll down to it)
A clean section with a small quiet heading (e.g. `WBTC price`) and the official TradingView Advanced
Real-Time Chart widget for `BINANCE:WBTCUSDT`, configured MINIMAL -- NO toolbars/buttons:
```
<script type="text/javascript" src="https://s3.tradingview.com/external-embedding/embed-widget-advanced-chart.js" async>
{ "symbol": "BINANCE:WBTCUSDT", "theme": "light", "style": "3", "autosize": true,
  "hide_top_toolbar": true, "hide_side_toolbar": true, "hide_legend": false,
  "allow_symbol_change": false, "save_image": false, "details": false, "hotlist": false,
  "calendar": false, "withdateranges": false }
</script>
```
In a rounded white card with a fixed reserved height (~360-440px desktop, ~300px mobile -- no layout shift).
`style:"3"` = a clean area chart. No symbol search, no toolbar buttons -- just the clean live WBTC chart.

## Section 3 -- WBTC AUTHORITIES (directly BELOW the chart)
A small quiet label (e.g. `Verified across WBTC authorities` / `Sources`) then a tidy row of these FIVE WBTC
super-authorities, each = its REAL LOGO + name, linked. Use EXACTLY (name | favicon domain | link), do NOT
alter the URLs:
- CoinGecko | coingecko.com | https://www.coingecko.com/en/coins/wrapped-bitcoin
- CoinMarketCap | coinmarketcap.com | https://coinmarketcap.com/currencies/wrapped-bitcoin/
- Gemini (What is WBTC) | gemini.com | https://www.gemini.com/cryptopedia/wbtc-what-is-wrapped-bitcoin
- Proof of Reserve (Chainlink) | bitgo.com | https://blog.bitgo.com/chainlink-brings-onchain-proof-of-reserve-to-wbtc-fcda00f2815c
- Bitstamp (WBTC guide) | bitstamp.net | https://www.bitstamp.net/learn/cryptocurrency-guide/what-is-wrapped-bitcoin-wbtc/
LOGOS via the Google favicon service ONLY: `https://www.google.com/s2/favicons?sz=64&domain=<DOMAIN>` (create
NO local files). Each logo `<img>`: width+height (e.g. 22x22), `loading="lazy"`, `alt=""`, `onerror="this.remove()"`.
Style: uniform rounded chips, muted by default, gently colorize + lift on hover; tidy single row (wraps on
mobile). Each link `target="_blank" rel="nofollow noopener noreferrer"`. No horizontal overflow.

## Footer
A `Stake WBTC &mdash; 2026` brand line + ONE educational line:
`Information on this page is for educational purposes only and is not financial advice.`

## CTAs + Claims
- Exactly TWO CTAs, distinct, both -> the preserved target href, `rel="noopener noreferrer"`: hero `Enter App`
  + card `Start Staking`. No third CTA, no topbar button.
- Confident premium copy; two floors: (1) NO invented numbers (no APY/stats/rewards typed -- the TradingView
  widget shows the only price); (2) no "guaranteed / risk-free / 100%", no fake wallet-connect.

## Technical / mobile
- SEO content in SOURCE HTML; tiny INLINE `<script>` only for any preview toggle (the TradingView embed is the
  one allowed external script). Every LOCAL `<img>` has width+height.
- Page scrolls; `overflow-x:hidden` on html/body; reserve the chart container height (no CLS). Respect `prefers-reduced-motion`.
- MOBILE CLEAN: single column; cards full-width; chart ~300px; authorities wrap to a tidy block; comfortable
  spacing + tap targets; NO horizontal overflow.
- Keep `lang="en"`; keep favicon/og/manifest/robots/sitemap referenced. HTML entities, no literal non-ASCII.

## Self-QC
- [ ] LIGHT premium 2026, Bitcoin-orange; modern refined buttons (arrow nudge); NOT dry.
- [ ] Topbar = THREE WBTC authorities (WBTC / BitGo / Etherscan), in source HTML.
- [ ] One `<h1>` = `Stake WBTC`; NO `<h2>`; deck `<p>` == meta description; H1 ~80px.
- [ ] Hero first screen; PAGE SCROLLS to chart + authorities; no horizontal overflow desktop/mobile.
- [ ] Clean TradingView `BINANCE:WBTCUSDT` chart: no toolbars/buttons, reserved height, light theme.
- [ ] FIVE WBTC authorities BELOW the chart with the EXACT URLs, real logos via Google favicon, nofollow, tidy.
- [ ] STAKE-console preview (NOT a swap): WBTC as a styled TEXT chip (no fabricated icon), number-free, `Start Staking`.
- [ ] Exactly TWO CTAs (`Enter App` + `Start Staking`) -> target; no topbar button.
- [ ] LOCAL images byte-untouched; favicon still the icon + brand mark; footer brand line + one educational line.

Make it genuinely premium, 2026-modern, with a clean WBTC chart and tasteful authorities. Then stop.
