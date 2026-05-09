# OptionsGuru — Options Analytics Platform

![Status](https://img.shields.io/badge/Status-Live-brightgreen)
![Deploy](https://img.shields.io/badge/Deploy-Vercel-black?logo=vercel)
![Language](https://img.shields.io/badge/Built%20with-HTML%20%7C%20JS%20%7C%20CSS-orange)
![Market](https://img.shields.io/badge/Market-NYSE%20%7C%20NASDAQ%20%7C%20BYMA-blue)
![Model](https://img.shields.io/badge/Model-Black--Scholes-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> Real-time options analyzer powered by **Black-Scholes pricing** and full **Greeks calculation**. Evaluates calls and puts across NYSE, NASDAQ, and BYMA — scoring each contract by edge, IV/HV ratio, and signal quality to identify optimal entry points.

🔗 **Live demo:** [option-guru.vercel.app](https://option-guru.vercel.app)

---

## 📸 Preview

![OptionsGuru Dashboard](screenshot.png)

*Cyberpunk-themed dashboard — Black-Scholes pricing, full Greeks, Edge $, IV/HV ratio, and AI-style signals per contract.*

---

## 🧠 How It Works

OptionsGuru takes a ticker and spot price as input, then calculates the **theoretical fair value** of each option contract using the Black-Scholes model. It compares this against the market price to detect **edge** — contracts where the market is mispricing volatility.

```
Inputs:
  Ticker · Spot Price · Historical Vol (HV%) · RSI · Risk-Free Rate

Black-Scholes Engine:
  BS Just Price = f(S, K, T, r, σ)
  Edge $ = BS Price − Market Price
  IV % = Implied Volatility from market price
  IV/HV = Volatility ratio (key signal indicator)

Greeks:
  Delta · Gamma · Theta · Vega

Scoring:
  Score = weighted combination of Edge, IV/HV, DTE, RSI
  Signal = OPTIMAL / ATM / ITM / OTM classification
```

---

## ✨ Features

| Feature | Detail |
|---|---|
| **Black-Scholes pricing** | Theoretical fair value per contract |
| **Full Greeks** | Delta, Gamma, Theta, Vega per strike |
| **Edge $ calculator** | Market price vs BS fair value |
| **IV % & IV/HV ratio** | Volatility regime detection |
| **Scoring system** | Ranks contracts by opportunity quality |
| **Buy/Sell signals** | OPTIMAL flag for best risk/reward setups |
| **Call/Put filter** | Separate tabs for calls and puts |
| **ATM / ITM / OTM filter** | Filter by moneyness |
| **Expiration filter** | Filter by DTE (days to expiration) |
| **Export CSV** | Download full options chain for offline analysis |
| **Multi-market** | NYSE, NASDAQ, and BYMA (Argentine market) |

---

## 📐 Black-Scholes Implementation

The model prices European-style options using:

```
d1 = [ln(S/K) + (r + σ²/2) × T] / (σ × √T)
d2 = d1 − σ × √T

Call = S × N(d1) − K × e^(−rT) × N(d2)
Put  = K × e^(−rT) × N(−d2) − S × N(−d1)
```

Where:
- `S` = Spot price
- `K` = Strike price
- `T` = Time to expiration (years)
- `r` = Risk-free rate
- `σ` = Historical volatility (HV)
- `N()` = Cumulative normal distribution

---

## 📊 Output Columns

| Column | Description |
|---|---|
| `Strike` | Contract strike price |
| `Expiration` | Expiry date |
| `DTE` | Days to expiration |
| `MKT USD` | Current market price of the option |
| `BS Justo` | Black-Scholes theoretical fair price |
| `Edge $` | Mispricing: BS price − Market price |
| `IV %` | Implied volatility extracted from market price |
| `IV/HV` | IV vs Historical Vol ratio |
| `Delta` | Price sensitivity to underlying movement |
| `Gamma` | Rate of change of Delta |
| `Theta` | Daily time decay |
| `Vega` | Sensitivity to volatility changes |
| `Score` | Composite opportunity score |
| `Señal` | OPTIMAL / standard classification |

---

## 🚀 Quick Start

No installation required — runs entirely in the browser.

**Option 1 — Use the live app:**
```
https://option-guru.vercel.app
```

**Option 2 — Run locally:**
```bash
git clone https://github.com/cris-devtrading/Option_guru
cd Option_guru
# Open index.html in your browser
```

**How to use:**
1. Enter a ticker (e.g. `GGAL`, `AAPL`, `NVDA`)
2. Set the current spot price in USD
3. Adjust Historical Volatility %, RSI, and Risk-Free Rate
4. Click **ANALIZAR**
5. Review calls and puts — filter by ATM/ITM/OTM or expiration
6. Sort by **Score** or **Edge $** to find the best setups
7. Export to CSV for further analysis

---

## 🛠️ Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — zero dependencies
- **Black-Scholes model** — implemented natively in JS
- **Vercel** — instant global deployment

---

## 💡 Use Cases

- **Retail options traders** identifying mispriced contracts on NYSE/BYMA
- **Prop traders** scanning volatility edge before expiration
- **Fintech developers** needing an embeddable options pricing component
- **Students & researchers** learning Greeks and Black-Scholes in practice

---

## 👤 About the Author

Built by **Cristian Chaves** — Algorithmic Trading & Fintech Developer.

Specializing in automated trading systems, broker API integrations, options analytics, and real-time financial dashboards for retail traders, prop firms, and fintech startups.

🔗 [AlgoTrader Pro — IBKR Automated Bot](https://github.com/cris-devtrading/algotrader-pro)  
🔗 [CCL Radar v2 — Argentine ADR/CEDEAR Monitor](https://ccl-radar.vercel.app)  
🔗 [BotSignal Latam — Telegram Signal Channel](https://botsignal.vercel.app)  
📧 Open for freelance projects — [Upwork](https://www.upwork.com/freelancers/cristianchaves) | [Fiverr](https://www.fiverr.com/cristianchaves)
📧 Contacto: quantedgelatam@gmail.com
🌐 GitHub: github.com/cris-devtrading
---

## 📄 License

MIT — free to use, modify, and distribute with attribution.
