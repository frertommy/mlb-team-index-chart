# MLB Team-Index Chart — demo

A self-contained demo that turns a sports team-index price chart into a game-by-game trading view, built on [TradingView Lightweight Charts](https://www.tradingview.com/lightweight-charts/) (v5).

**Live:** open `index.html` (the trader view) — or `basic.html` for the bare chart.

## What it shows
A team's index price reacts in discrete jumps around games (win → up, loss → down), and the schedule tells you when the next move is coming. The view makes that legible:

- **Win/loss circles + top-axis flags** on each settled game, labelled with opponent + date.
- **Game strip** (click a chip — or any segment — to zoom into that game; an on-chart "Zoom out" returns to the overview).
- **Hover card** on each game with the score and the price move, plus prev / zoom / next.
- **Form & momentum** header (record, streak, last-10) and a **next-game card** with empirical win/loss price targets.
- Timeframes, candle/line, indicators, dividers, and target toggles.

## How it works
- Raw event-driven price ticks are bucketed into OHLC client-side at the selected timeframe.
- Game markers are placed on the **settlement tick** (when the result posts to the index), with opponent/score/date overlaid.
- Data here is a **static snapshot** bundled as JSON (`mlb-prices.json`, `mlb-games.json`, `mlb-next.json`) so the page runs with no backend.

No build step — it's plain HTML/CSS/JS plus the Lightweight Charts CDN.
