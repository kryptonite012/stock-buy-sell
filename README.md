# Bazaar — Indian Stock Trading Simulator

A lightweight, single-file paper trading app for Indian stocks. Built with plain HTML, CSS, and JavaScript — no frameworks, no backend, no setup required.

![HTML](https://img.shields.io/badge/HTML-single%20file-orange) ![License](https://img.shields.io/badge/license-MIT-blue) ![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)

---

## Demo

Open `bazaar.html` directly in your browser. That's it.

---

## Features

- **20 real NSE & BSE stocks** across 9 sectors
- **Buy & sell** with a clean order modal
- **Three order types** — Market, Limit, and Stop-Loss
- **Portfolio view** with a doughnut chart showing allocation by stock
- **Per-holding P&L** — profit/loss in ₹ and percentage
- **Trade history** with timestamps in IST
- **Sector filter** and live stock search
- **NIFTY 50, SENSEX, Bank NIFTY** index bar
- **Dark mode** support via CSS variables
- Fully responsive — works on mobile and desktop

---

## Getting Started
```bash
# Clone the repo
git clone https://github.com/your-username/bazaar.git

# Open in browser
open bazaar.html
```

No npm install. No build step. No server needed.

---

## Stocks Included

| Ticker | Company | Sector | Exchange |
|---|---|---|---|
| RELIANCE | Reliance Industries | Energy | NSE |
| TCS | Tata Consultancy Services | IT | NSE |
| HDFCBANK | HDFC Bank | Banking | NSE |
| INFY | Infosys | IT | NSE |
| ICICIBANK | ICICI Bank | Banking | NSE |
| HINDUNILVR | Hindustan Unilever | FMCG | BSE |
| ITC | ITC Limited | FMCG | NSE |
| SBIN | State Bank of India | Banking | NSE |
| BAJFINANCE | Bajaj Finance | NBFC | NSE |
| WIPRO | Wipro | IT | NSE |
| TATAMOTORS | Tata Motors | Auto | NSE |
| MARUTI | Maruti Suzuki | Auto | NSE |
| SUNPHARMA | Sun Pharmaceutical | Pharma | NSE |
| DRREDDY | Dr. Reddy's Laboratories | Pharma | BSE |
| ONGC | ONGC | Energy | NSE |
| POWERGRID | Power Grid Corp. | Utilities | NSE |
| TITAN | Titan Company | Consumer | NSE |
| ADANIPORTS | Adani Ports | Infra | NSE |
| LTIM | LTIMindtree | IT | NSE |
| COALINDIA | Coal India | Energy | NSE |

---

## How It Works

### Starting balance
Every session begins with ₹1,00,000 in virtual cash.

### Placing an order
1. Go to the **Market** tab
2. Search or filter by sector to find a stock
3. Click **Buy** — a modal opens showing the stock price, order type selector, and quantity controls
4. Adjust quantity with +/− buttons, review the total cost, and click **Place buy order**

Selling works the same way — a **Sell** button appears on any stock you currently hold, both in the Market tab and the Portfolio tab.

### Order types
- **Market** — executes immediately at the listed price
- **Limit** — label only in this simulator; executes at the listed price
- **SL (Stop-Loss)** — label only in this simulator; executes at the listed price

### Portfolio
The Portfolio tab shows a live doughnut chart of your holdings by value, along with a breakdown of each position — shares held, average cost, current value, and unrealised P&L.

### History
Every trade is logged with ticker, order type, quantity, price per share, total value, and time in IST.

---

## Project Structure
```
bazaar/
└── bazaar.html      # Entire app — HTML, CSS, and JS in one file
└── README.md
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 with custom properties (light/dark mode) |
| Logic | Vanilla JavaScript (ES6+) |
| Chart | [Chart.js 4.4.1](https://www.chartjs.org/) via CDN |

---

## Customisation

All stock data lives in the `STOCKS` array near the top of the `<script>` block in `bazaar.html`. Each entry looks like this:
```js
{ t:'INFY', n:'Infosys', p:1482.30, c:+1.10, s:'IT', ex:'NSE' }
```

| Key | Meaning |
|---|---|
| `t` | Ticker symbol |
| `n` | Company name |
| `p` | Price (₹) |
| `c` | Daily change (%) |
| `s` | Sector |
| `ex` | Exchange (NSE or BSE) |

To change the starting cash, find this line and update the value:
```js
let cash = 100000;
```

---

## Limitations

- **Prices are static** — they do not update in real time. This is a simulator, not a live trading platform.
- **State is not persisted** — refreshing the page resets your cash, holdings, and history. To add persistence, hook into `localStorage`.
- **Order types are cosmetic** — Market, Limit, and SL all execute at the same listed price in this version.
- **Not financial advice** — this project is for educational and project purposes only.

---

## Roadmap ideas

- [ ] localStorage persistence so state survives page refresh
- [ ] Simulated real-time price fluctuations
- [ ] Functional limit and stop-loss order logic
- [ ] Candlestick mini-charts per stock
- [ ] Export trade history as CSV
- [ ] Watchlist tab

---

## License

MIT — free to use, modify, and distribute.

---

> Built as a frontend project to demonstrate a clean, dependency-light trading UI using real Indian market stocks.
