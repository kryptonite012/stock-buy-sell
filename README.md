# Bazaar — Indian Stock Trading Simulator

A lightweight, single-file paper trading app for Indian stocks. Built with plain HTML, CSS, and JavaScript — no frameworks, no backend, no setup required.


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

Bazaar is a self-contained paper trading simulator for Indian equity markets. It ships as a single HTML file — no build tools, no npm, no server. Drop it in a folder, open it, and start trading.
It covers 20 large-cap Indian stocks across 9 sectors — from Reliance and TCS to Titan and Coal India — with a portfolio tracker, doughnut allocation chart, per-holding P&L, and full trade history. Think of it as a fast, frictionless way to learn how equity trading works without risking real money.

Features
📈 Trading

Buy and sell across 20 NSE & BSE stocks
Three order types — Market, Limit, Stop-Loss
Clean order modal with +/− quantity controls and real-time total cost display
Sells are gated — you can only sell what you hold

💼 Portfolio

Live doughnut chart showing allocation by stock value
Per-position breakdown: shares held · average cost · current value · unrealised P&L (₹ and %)
Sell directly from the Portfolio tab

📊 Market

Sector filter — Banking, IT, FMCG, Pharma, Auto, and more
Live stock search by name or ticker
NIFTY 50, SENSEX, Bank NIFTY index bar at the top

🕐 History

Every trade logged: ticker · order type · quantity · price · total · timestamp in IST

🎨 UI/UX

Dark mode via CSS custom properties — no flash, no JS required
Fully responsive — works on mobile and desktop
No external fonts or icon packs loaded


Getting Started
bash# Option 1 — Clone
git clone https://github.com/your-username/bazaar.git
cd bazaar
open bazaar.html          # macOS
start bazaar.html         # Windows
xdg-open bazaar.html      # Linux

# Option 2 — Download
# Download bazaar.html from Releases → open in any browser
That's it. No npm install. No build step. No server. No .env file.
Browser compatibility: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

How It Works
Starting balance
Every session begins with ₹1,00,000 in virtual cash.
Placing a buy order

Go to the Market tab
Search by ticker or filter by sector
Click Buy on any stock
In the modal — select order type, adjust quantity with +/− buttons, review total cost
Click Place buy order — your cash is debited, the holding appears in Portfolio

Placing a sell order
A Sell button appears on any stock you hold — both in the Market tab and the Portfolio tab. The modal shows your average buy price alongside the current price so you can see your P&L before confirming.
Order types
TypeBehaviour in this versionMarketExecutes immediately at the listed priceLimitUI label only — executes at listed priceSL (Stop-Loss)UI label only — executes at listed price
Functional limit and SL logic is on the roadmap.
P&L calculation
Unrealised P&L  =  (Current Price − Average Buy Price) × Shares Held
P&L %           =  (Unrealised P&L / Total Cost Basis) × 100
Average buy price is recalculated on each subsequent buy using a weighted average.

Stock Universe
20 large-cap Indian stocks across 9 sectors:
TickerCompanySectorExchangeRELIANCEReliance IndustriesEnergyNSEONGCONGCEnergyNSECOALINDIACoal IndiaEnergyNSETCSTata Consultancy ServicesITNSEINFYInfosysITNSEWIPROWiproITNSELTIMLTIMindtreeITNSEHDFCBANKHDFC BankBankingNSEICICIBANKICICI BankBankingNSESBINState Bank of IndiaBankingNSEBAJFINANCEBajaj FinanceNBFCNSEHINDUNILVRHindustan UnileverFMCGBSEITCITC LimitedFMCGNSETATAMOTORSTata MotorsAutoNSEMARUTIMaruti SuzukiAutoNSESUNPHARMASun PharmaceuticalPharmaNSEDRREDDYDr. Reddy's LaboratoriesPharmaBSEPOWERGRIDPower Grid Corp.UtilitiesNSETITANTitan CompanyConsumerNSEADANIPORTSAdani PortsInfraNSE

Project Structure
bazaar/
├── bazaar.html      ← entire app (HTML + CSS + JS in one file)
└── README.md
Inside bazaar.html
bazaar.html
├── <head>           CSS custom properties (light + dark theme tokens)
├── <body>
│   ├── Index bar    NIFTY 50 · SENSEX · Bank NIFTY
│   ├── Tabs         Market / Portfolio / History
│   ├── Market tab   Search · Sector filter · Stock cards
│   ├── Portfolio tab Doughnut chart · Holdings table
│   └── History tab  Trade log
└── <script>
    ├── STOCKS[]     Stock data array (edit this to customise)
    ├── State        cash · holdings · trades
    └── Functions    render* · placeOrder · updatePortfolio

Tech Stack
ConcernChoiceWhyMarkupHTML5Single-file portabilityStylingCSS3 + custom propertiesZero-JS theming, light/dark modeLogicVanilla JS (ES6+)No build toolchain, instant loadChartsChart.js 4.4.1 via CDNBest-in-class canvas charts, small footprint
No frameworks. No bundler. No transpilation. The entire app is human-readable source.

Customisation
Adding or editing stocks
All stock data lives in the STOCKS array near the top of the <script> block:
jsconst STOCKS = [
  { t: 'INFY',  n: 'Infosys',              p: 1482.30, c: +1.10, s: 'IT',      ex: 'NSE' },
  { t: 'SBIN',  n: 'State Bank of India',  p:  812.45, c: -0.35, s: 'Banking', ex: 'NSE' },
  // add your own below ↓
  { t: 'NYKAA', n: 'FSN E-Commerce',       p:  178.90, c: +2.45, s: 'Consumer',ex: 'NSE' },
];
KeyTypeDescriptiontstringTicker symbol (e.g. 'RELIANCE')nstringCompany display namepnumberPrice in ₹cnumberDaily change in % (positive or negative)sstringSector — used by the filter dropdownexstringExchange — 'NSE' or 'BSE'
Changing the starting cash
Find this line in the <script> block and update the value:
jslet cash = 100000;   // ← change to any amount (in ₹)
Persisting state across refreshes
Bazaar resets on every page refresh. To make trades persist, wrap the state variables in localStorage:
js// Save
localStorage.setItem('bazaar_state', JSON.stringify({ cash, holdings, trades }));

// Load on startup
const saved = JSON.parse(localStorage.getItem('bazaar_state') || 'null');
if (saved) { cash = saved.cash; holdings = saved.holdings; trades = saved.trades; }
Simulating price movement
Prices are static by default. To add random fluctuation, drop this snippet into the script:
jssetInterval(() => {
  STOCKS.forEach(stock => {
    const delta = (Math.random() - 0.499) * 0.4;   // ±0.2% per tick
    stock.p = parseFloat((stock.p * (1 + delta / 100)).toFixed(2));
  });
  renderMarket();
  renderPortfolio();
}, 3000);   // every 3 seconds

Limitations
LimitationDetailStatic pricesPrices do not update. This is a simulator, not a live feed.No persistenceRefreshing the page resets all state. See Customisation for localStorage tips.Cosmetic order typesMarket, Limit, and SL all execute at the same listed price.No fractional sharesQuantity is always a whole number.Not financial adviceFor educational and learning purposes only.

Roadmap

 localStorage persistence — state survives page refresh
 Simulated real-time price fluctuations with configurable volatility
 Functional limit orders — queue and execute when price is hit
 Functional stop-loss — auto-sell when price drops below trigger
 Candlestick mini-charts per stock (simulated OHLC)
 Export trade history as CSV
 Watchlist tab — track stocks without buying
 Brokerage fee simulation (₹20 flat or percentage)
 Portfolio performance graph over time
 Multi-session leaderboard via localStorage


Contributing
Pull requests are welcome. For major changes, open an issue first to discuss what you'd like to change.
bashgit clone https://github.com/your-username/bazaar.git
# Edit bazaar.html in any text editor
# Test in browser — no build step needed
# Open a PR

🚀 Live Features
💹 Real-time price simulation
🛒 Buy & Sell stocks (Market, Limit, Stop-Loss orders)
📊 Portfolio tracking with P&L analytics
⭐ Watchlist management
📜 Trade history with CSV export
📉 Interactive charts using Chart.js
🌙 Dark / Light theme toggle
💾 LocalStorage-based persistence

🧠 Key Concepts Implemented
DOM Manipulation
Event Handling
State Management (LocalStorage)
Financial Calculations (P&L, Avg Price)
Chart Visualization
Order Execution Logic (Market + Pending Orders)
🖥️ Tech Stack
Frontend: HTML5, CSS3, JavaScript (Vanilla)
Charts: Chart.js
Storage: Browser LocalStorage
