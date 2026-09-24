# 🎰 Lucky Bull Casino

### A stock-market-powered virtual casino for players who like their market data with a little more drama. Its interface is gambling based but you actually stacking on real time stocks 

**Lucky Bull Casino** is a self-contained browser game built around a hidden market move. Choose a side, place demo dollars on a table, and let a live quote—or a transparent fallback simulation—decide whether the pit pays out.

> **Play now:** [white-flower-deaths.github.io/lucky-bull-stocks-casino/casino.html](https://white-flower-deaths.github.io/lucky-bull-stocks-casino/casino.html)

This is a **virtual sandbox only**. It does not accept deposits, process withdrawals, or place trades. No real money is involved.

---

## ✨ What makes it fun

- **Three fast casino games:** coin flip, high card, and dice roll.
- **Five themed tables:** each table hides a different market basket.
- **Real market movement under the hood:** quotes are fetched from the free Stooq CSV endpoint when available.
- **Automatic live-feed hunting:** stale or sleeping symbols are replaced with a fresh symbol when possible.
- **A safe fallback:** if the feed is unavailable, the round uses an anchored simulation instead of freezing.
- **Big reveal moments:** animated cards, dice, coin flips, result modals, confetti, money showers, streaks, and dealer commentary.
- **Persistent demo accounts:** balances, round history, win rate, P&L, and equity curve are saved in the browser.
- **45 rotating star portraits:** the pit has a new host every few seconds.
- **Sound controls:** use the included `music.mp3` when available, or fall back to a synthesized Web Audio casino groove.
- **Responsive layout:** designed for desktop, tablet, and mobile browsers.

## 🎲 The games

| Game | Your choice | Leverage | How the reveal works |
| --- | --- | ---: | --- |
| 🪙 Coin Flip | **Bull / Heads** or **Bear / Tails** | 20× | The market move determines which side lands. |
| 🃏 High Card | **Ace** or **Joker** | 50× / 30× | A matching house card creates the winning reveal. |
| 🎲 Dice Roll | **High** or **Low** | 40× | The displayed dice land on your side; a six is a push. |
| 😶‍🌫️Characters board | **SEXY** or **INTRESTING** | 40× | The side display will pop up some unique and fan favorite characters or some random beauty to encourage you for the love of the game|

Each round offers a buy-to-sell window of **15 seconds, 30 seconds, 1 minute, 3 minutes, or 5 minutes**. A round can also be closed early with the cash-out control.

## 💰 How payouts work

The game uses demo dollars and a market-style calculation:

```text
return = stake + (stake × market move × leverage)
```

The result is bounded by the game rules:

- **Maximum loss:** your stake.
- **Maximum win:** 5× your stake in profit.
- **Flat move:** a push; your stake is returned.
- **Early cash-out:** available during an active round and settled at the app's early-exit rate.

### Example

With a `$100` stake, a `+0.37%` move, and `50×` leverage:

```text
profit = $100 × 0.0037 × 50 = $18.50
return = $118.50
```

The app keeps the ticker and price hidden during play. You see the market state, the round timer, and the final theatrical reveal—not a trading terminal.

## 📡 Market-feed behavior

Lucky Bull polls the Stooq CSV endpoint:

```text
https://stooq.com/q/l/
```

The visible table names are fictional, while the hidden baskets use liquid market symbols such as:

- **Dragon's Den:** NVDA, TSLA, AMD
- **Eagle Nest:** AAPL, MSFT, AMZN
- **Diamond Vault:** META, NFLX, COIN
- **Rocket Fuel:** TSLA, NVDA, MSTR
- **Midnight Desk:** BTCUSD, ETHUSD, COIN, MSTR

The pit boss checks whether quotes have actually moved recently. If a selected table is stale, the app searches another table and then a liquid fallback symbol. If the network request fails completely, it uses a local random-walk simulation so the UI remains playable.

The app locks a round to its source: a live round settles from live data, while a simulated round stays on its own simulation path. A feed problem cannot silently switch the source halfway through a bet.

## 🚀 Play locally

No package manager, server, or build step is required.

### Option 1: open the file

1. Download or clone this repository.
2. Open `casino.html` in a modern browser.
3. Choose a player name and starting demo balance.
4. Allow or mute sound when prompted.

### Option 2: serve the folder locally

A local HTTP server can provide a more consistent browser experience for audio and network requests:

```powershell
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/casino.html
```

## 🌐 GitHub Pages

This repository is already configured as a static site. GitHub Pages serves the game directly from the `main` branch.

1. Open the repository's **Settings**.
2. Select **Pages**.
3. Set the source to **Deploy from a branch**.
4. Select **`main`** and the **`/ (root)`** folder.
5. Save and wait for the deployment to finish.

The playable page is:

```text
https://white-flower-deaths.github.io/lucky-bull-stocks-casino/casino.html
```

Because the app entry point is `casino.html`, the `/casino.html` suffix is required.

## 📁 Project structure

```text
lucky-bull-casino/
├── casino.html       # Complete game: markup, styles, and JavaScript
├── music.mp3        # Optional looping soundtrack used when supported
├── stars/            # 45 rotating PNG star portraits
├── .gitignore
└── README.md
```

The project intentionally has **no build pipeline and no runtime dependencies**.

## 💾 Privacy and browser storage

Player accounts and game history are stored locally in the browser with `localStorage`.

- No account server is used.
- No password is required.
- Data is tied to the current browser profile and origin.
- Clearing site data removes the local demo accounts and history.
- The live-feed request goes to Stooq from the browser when the game is running.

Do not enter real credentials or sensitive personal information into the demo account fields.

## 🛠️ Customization

The game is intentionally easy to modify:

- Change table names and hidden baskets in the `TABLES` constant.
- Adjust round lengths in `DURATIONS`.
- Tune the push threshold with `PUSH_BAND`.
- Replace or add portraits in `stars/`.
- Replace `music.mp3` with an audio file you are legally permitted to distribute.
- Change colors, animations, and layout in the `<style>` block.

If you add or replace artwork, music, or other third-party assets, verify that your license permits redistribution in a public repository.

Some example images are :
<img width="1920" height="1080" alt="Screenshot 2026-09-25 000624" src="https://github.com/user-attachments/assets/cb8b88b6-abfd-4457-9a2d-2dbc81a8b7d0" />

<img width="1920" height="1080" alt="Screenshot 2026-09-25 000723" src="https://github.com/user-attachments/assets/10d7f4a5-c4fb-4a9f-9e6f-ed80d707b2e0" />

<img width="1920" height="1080" alt="Screenshot 2026-09-25 000843" src="https://github.com/user-attachments/assets/47b82b7d-8c18-43d5-94df-b784d0b3436b" />

<img width="1920" height="1080" alt="Screenshot 2026-09-25 000909" src="https://github.com/user-attachments/assets/7da9afb2-000c-41d2-8dfb-4315a0bb9055" />

<img width="1920" height="1080" alt="Screenshot 2026-09-25 000947" src="https://github.com/user-attachments/assets/2923a733-4757-4530-b371-72fb2ec8bad2" />

<img width="1920" height="1080" alt="Screenshot 2026-09-25 001016" src="https://github.com/user-attachments/assets/01b3416e-fb46-4c98-be76-5f50b3359062" />




## ⚠️ Responsible-use notice

Lucky Bull Casino is an entertainment and programming project using fictional balances. It is **not** a financial product, trading tool, investment recommendation, gambling service, or source of financial advice. Market data may be delayed, unavailable, incomplete, or simulated. Never use the game's results to make real-world financial decisions.(Until and Unless you are really GAMBLING)

## 📄 License

Only the copyright free assets are used.
