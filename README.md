# AlgoTrading_CW2: Term-Structure Strategy on U.S. Treasuries

Coursework 2 for COMP0051 (Algorithmic Trading). This repository researches, implements, and evaluates a rules-based strategy that trades a long-duration U.S. Treasury ETF using short-rate information.

---

## Repository Contents

- `CW2_Notebook.ipynb` - end to end research notebook (data preparation, signals, backtest, analysis)
- `SPTL.csv` - historical prices for SPDR Portfolio Long Term Treasury ETF (SPTL)
- `EFFR_rates.xlsx` - Effective Federal Funds Rate time series
- `COMP0051 - Coursework 2.pdf` - assignment brief
- `README.md` - project documentation

---

## Project Objective

Design and assess an algorithmic strategy that trades long-duration U.S. Treasuries using information from the Effective Federal Funds Rate (EFFR).

Workflow:
1. Ingest and clean price data for SPTL and macro data for EFFR.
2. Engineer signals from the rates series, for example level, change, momentum, and regime filters.
3. Backtest a long or long-flat strategy on SPTL with realistic frictions.
4. Evaluate performance and robustness, including transaction costs and parameter sensitivity.

---

## Strategy Overview

- Signal family: term structure and policy-rate dynamics derived from EFFR  
  Examples: month-over-month change in EFFR, moving average slope, rising vs falling rate regimes.
- Positioning: increase or maintain exposure to SPTL when the signal indicates falling or peaking policy rates, reduce or exit when rates are rising.
- Risk and execution:
  - Rebalance frequency: daily or weekly, parameterized in the notebook
  - Transaction cost assumption: configurable basis points per trade
  - Optional constraints: volatility cap or drawdown limit

---

## Result Outputs

The notebook generates:
- Equity curve vs buy and hold
- Rolling Sharpe and drawdowns
- Return attribution by regime
- Parameter sensitivity, where applicable

Run the notebook to reproduce figures and tables for your environment and data horizon.

---

## Quickstart

### Environment

Python 3.10 or newer is recommended.

Install common dependencies:
```bash
pip install pandas numpy matplotlib scipy statsmodels jupyter
