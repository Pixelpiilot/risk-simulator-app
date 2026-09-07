# Risk Simulator

Compounding lot-size cascade simulator with capital risk cap, slippage,
turnover fees, and an Indian-market (Day/F&O whole-lot) mode. Built with
React + Vite + Tailwind CSS + Recharts.

## Modes

- **Single Run** — fractional-lot cascade with per-lot or turnover-based fees.
- **Win Rate Sweep** — runs the same strategy config across win rates from
  0% to 100% (in configurable steps), averaging N random runs per point.
- **Day / F&O** — whole-number lots and lot size (e.g. Nifty), fixed or
  turnover brokerage, plus a separate "Other Charges %" (STT, stamp duty,
  exchange charges, GST).

## Setup

```bash
npm install
npm run dev
```

Then open the printed local URL (default `http://localhost:5173`).

## Build for production

```bash
npm run build
npm run preview
```

The production build is output to `dist/`.

## Project structure

```
risk-simulator/
├── index.html
├── package.json
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
└── src/
    ├── main.jsx        # React entry point
    ├── App.jsx         # RiskSimulator component (all simulation logic + UI)
    └── index.css       # Tailwind directives
```

All simulation logic (cascade sizing, fees, slippage, spread cost, drawdown
caps, win-rate sweep) lives in `src/App.jsx`.
