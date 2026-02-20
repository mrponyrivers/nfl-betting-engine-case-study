# NFL POWERBOOK — Professional Betting Engine (Case Study)

A public **case study** of a professional-grade NFL betting workflow engine I built (“NFL POWERBOOK”).
This repo showcases **workflow engineering, automation, and evaluation** while keeping sensitive/proprietary components private.

**What this case study demonstrates**
- Live odds ingestion → normalization → implied probability
- Model probability vs market probability
- Expected Value (EV) + Kelly stake sizing
- CLV tracking + bet logging + settlement history
- Reproducible weekly workflow and clean exports

---

## Why I built it

I wanted a system that treats betting as a **pricing + risk + process** problem:
- not just “pick the better team”
- but **consistently identify mispriced lines**, size stakes responsibly, and evaluate performance over time.

This project is also a strong example of what I enjoy building as an **AI Workflow Engineer**: turning messy real-world inputs into reliable outputs (structured data, exports, repeatable runs).

---

## What’s included in this public repo

✅ Included
- Architecture + workflow description
- Sample datasets (fake data) that mirror the real schemas
- Output conventions and what each artifact represents
- Screenshots (blurred/redacted)

🔒 Kept private (by design)
- API keys / endpoints
- Proprietary formulas, weights, thresholds
- Personal bankroll info
- Full workbook(s) with production logic
- Any bookmaker account details

---

## Core features

### Odds pipeline
- Ingest live sportsbook odds (moneyline/spread/totals)
- Normalize into a consistent “master feed”
- Convert odds → implied probability

### Model + decisioning
- Compare model probabilities to market implied probabilities
- Compute EV (edge) and flag value opportunities
- Recommend stake sizing with Kelly (or fractional Kelly)

### Tracking + evaluation
- Bet log ledger
- Settlement outputs (win/loss, units, ROI)
- CLV (Closing Line Value) tracking to measure whether bets beat the market

---

## Architecture (high level)

```mermaid
flowchart LR
  A[Live Odds Feed] --> B[Odds Normalization / Master Feed]
  C[Team Stats / Power Ratings] --> D[Model Probabilities]
  B --> E[Implied Probabilities]
  D --> F[EV + Kelly Decisioning]
  E --> F
  F --> G[Bet Log]
  G --> H[Settlement / History Ledger]
  B --> I[Closing Lines]
  G --> J[CLV Tracking]
  I --> J


---

## Screenshots (blurred/redacted)

These screenshots are intentionally blurred to protect sensitive details (keys, bankroll, proprietary thresholds).

- **System overview**
  ![](docs/screenshots/01_overview.png)

- **Odds normalization**
  ![](docs/screenshots/02_odds_normalization.png)

- **EV + Kelly recommendations**
  ![](docs/screenshots/03_ev_kelly.png)

- **Bet log + settlement**
  ![](docs/screenshots/04_betlog_settlement.png)

- **CLV tracking (optional)**
  ![](docs/screenshots/05_clv.png)
