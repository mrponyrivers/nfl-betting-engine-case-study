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

## Walkthrough video

YouTube demo (unlisted): https://www.youtube.com/watch?v=xI88nChjKWU

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
--
Weekly workflow (how it runs)

Update odds

Pull latest odds and normalize to a master table

Update model inputs

Refresh team stats / power ratings

Generate model probabilities

Compare vs market

Market implied probability vs model probability

Compute EV, select candidates

Size stakes

Kelly (or fractional Kelly) based on edge + price

Log bets

Store entry lines + odds + timestamp

Track CLV + settle

Compare to closing line

Record results and update history metrics

Sample data (safe, fake)

This repo includes fake samples to show schemas and outputs:

samples/sample_odds.csv

samples/sample_model_probs.csv

samples/sample_bet_log.csv

samples/sample_outputs.csv

Outputs (what the engine produces)

Typical output artifacts:

Clean normalized odds feed

Model probability table

EV / Kelly recommendation table

Bet log (entries)

Settlement ledger (results)

CLV report (entry vs close)

Screenshots (blurred/redacted)

These screenshots are intentionally blurred to protect sensitive details (keys, bankroll, proprietary thresholds).

Put your images in docs/screenshots/ and name them like the examples below.

System overview


Odds normalization


EV + Kelly recommendations


Bet log + settlement


CLV tracking (optional)


Responsible note

This project is shared as a workflow/engineering case study. Betting involves risk and variance. Any system like this should be evaluated with careful bankroll management and realistic expectations.

Links

GitHub profile: https://github.com/mrponyrivers

Streamlit demos hub: https://share.streamlit.io/user/mrponyrivers