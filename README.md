# Asset Pricing Assignment (CAPM • APT • Risk-Adjusted Performance)

This repository contains a **production-ready Jupyter Notebook (Python)** that:
- Downloads real market data (NYSE/USA example)
- Resamples to **monthly frequency** and builds **5-year** return series
- Implements **CAPM**, **APT (2-factor)**, and **risk-adjusted performance metrics**
- Produces tables + charts required by the assignment

## Data sources (auto-download)
- **Equities + Market Index**: Yahoo Finance via `yfinance`
- **Risk-free (3-month / 91-day T-bill rate)**: FRED series `TB3MS` (percent, monthly)
- **Macroeconomic factors (monthly)**: FRED series `CPIAUCSL` (CPI) and `FEDFUNDS` (Fed Funds)

> Note: Always respect the data provider Terms of Service. If any series fails to download (network restrictions), you can switch the notebook to **CSV mode**.

## How to run
1. Create/activate a Python environment.
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Open and run the notebook:
   - `notebooks/asset_pricing_models.ipynb`

## What you will edit
At the top of the notebook, set:
- `START_DATE`, `END_DATE` (5-year window)
- `ASSETS` (4 tickers, different sectors)
- `MARKET_TICKER` (e.g., `^NYA` or `^GSPC`)
- Factor series IDs (defaults are already set)

## Outputs
The notebook writes clean artifacts to:
- `data/processed/` (monthly prices/returns used in models)
- `outputs/` (tables as CSV + key charts)

## Exporting a PDF report
Two common options:
- Export the notebook to HTML and print-to-PDF from a browser.
- Use `jupyter nbconvert --to pdf notebooks/asset_pricing_models.ipynb` (requires a LaTeX distribution).
