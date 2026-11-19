# Memecoin Starter

A memecoin dashboard web app with a live token list, a new-token radar with a
21-check safety breakdown, a watchlist, price alerts, and an AI Token Analyst
powered by Firebase AI Logic (hybrid inference: Gemini Nano on-device in
Chrome when available, cloud Gemini fallback).

Built for the [#BuildHybridAI 2026](https://firebasehybridaihackathon.devpost.com/)
hackathon (Web / Chrome category).

## Live site

https://riu-ui.github.io/memecoin-starter/

## Features

- **Token list** — top memecoins with price, 24h change, market cap and volume.
- **New Token Radar** — freshly listed tokens with a 21-check automatic safety
  breakdown (liquidity, buy/sell flow, mint/freeze authority, RugCheck score,
  LP lock, holders and more). Results are shown inline on each card — no click
  needed.
- **Watchlist & price alerts** — saved per account in Firestore (sign-in
  required).
- **AI Token Analyst** — ask Gemini about any token, or generate a market
  brief for the whole list. Answers are grounded in the page's market data.
- **Themes** — three Firebase palettes, each with light and dark variants.

## Tech

- Single static page (`index.html`, no build step).
- Firebase Authentication (email/password) + Cloud Firestore.
- Firebase AI Logic SDK (hybrid inference, `PREFER_ON_DEVICE`).
- Market data is a snapshot taken at build time (see the date shown on the
  page); the page does not fetch new prices when opened.

## Run locally

Serve the folder over HTTP (module scripts and Firebase need a real origin),
for example:

```bash
python3 -m http.server 8000
```

then open http://localhost:8000.

To use your own Firebase project, replace `firebaseConfig` in `index.html`
with your own web app config, publish matching Firestore rules (the page
shows the rules it needs, with a Copy button), and enable AI Logic in the
Firebase console (Build → AI Logic → Get started).

## License

Apache License 2.0 — see [LICENSE](LICENSE).
