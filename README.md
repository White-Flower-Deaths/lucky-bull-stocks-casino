# 🎰 LUCKY BULL — Wall Street Casino (Virtual Sandbox)

**A stock-market-based gamble.** Call the coin toss, pick your card, roll the dice —
a hidden *real* market feed decides who takes the pot. All money is demo dollars.
No real-money betting, ever.

## ▶️ Play it

**Easiest (no setup):** download this repo, then double-click **`casino.html`**.
Works offline-capable in any modern browser (Chrome / Edge / Firefox).

**As a website (GitHub Pages):** any `*.html` in the repo gets its own link —
`.../casino.html` plays directly. (Only the bare repo URL needs an `index.html`.)

## 🎲 The games

| Game | Your call | Leverage | Reveal |
|------|-----------|----------|--------|
| 🪙 Coin | HEADS / TAILS | 20× | Lands your call = win |
| 🃏 Cards | ACE (50×) / JOKER (30×) | as shown | House pairs your card = win |
| 🎲 Dice | HIGH 6–12 / LOW 2–6 @ 40× | 40× | Lands your side = win, 6 = split |

**Payouts are proportional, like real investing:**
`profit/loss = stake × real market move × leverage`.
$100 + a 0.37% market rise on Ace (50×) = **$118.50 back**.
Wrong direction loses proportionally — never more than your stake
(max win 5× stake, max loss 1×, flat market = push/refund).

## ✨ Around the pit

- 📡 **Live hidden feed** (free Stooq quotes, no key) with auto-hunt: sleeping
  tables switch you to live symbols; total outage falls back to anchored sim.
  Prices are never shown — pure gamble feel.
- 🎰 **Home screen** with sign-in / create, lounging star portraits, token rain.
- ⭐ **45 rotating hostesses** (new one every 5s) that celebrate and roast you.
- 🔊 **Music**: drop any MP3 next to the file named `music.mp3` and it loops;
  otherwise a synthesized casino groove plays. 🎷 toggles, plus a sound
  permission gate on first open.
- 👤 **Demo accounts** saved in your browser, session stats, equity curve,
  early cash-out, rebet, win-streak banners.

## 📁 Structure

```
casino.html       ← the whole app (single file, no build step)
music.mp3       ← soundtrack (loops if present)
stars/          ← star portraits (star1.png … star45.png)
```

## ⚠️ Disclaimer

Demo dollars only. Not financial advice. Not affiliated with any exchange.
Artwork and music belong to their respective owners — see note below.

## 🎨 Art / music note

The `stars/` portraits and `music.mp3` are licensed assets owned by this
project (purchased with permission). Keep your license receipts with the
project — if you publish or fork publicly, they prove the art and music
are cleared.
