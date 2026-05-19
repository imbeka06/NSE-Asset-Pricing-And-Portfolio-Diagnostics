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
This repo is tested on **Windows + Python 3.13**.

### 1) Create a virtual environment
From the repository root:

- Create venv: `python -m venv .venv`
- Activate (PowerShell): `./.venv/Scripts/Activate.ps1`

### 2) Install dependencies
Inside the activated environment:

- `python -m pip install -r requirements.txt`

### 3) Run the model notebook
Open and run:

- `notebooks/asset_pricing_models.ipynb`

The notebook downloads/caches data (if needed), runs CAPM/APT/performance metrics, and writes tables/figures.

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

This repository also **tracks** the cached inputs and generated outputs so the project is self-contained:
- `data/raw/` contains the downloaded Yahoo Finance + FRED CSV caches
- `outputs/` contains regression summaries, tables, and charts used in the report

## Exporting a PDF report
Two common options:
- Use the included technical report template: `report/technical_report.md`.
   - Open it in VS Code Markdown preview (or GitHub) and **Print → Save as PDF**.
- Or export the notebook to HTML and print-to-PDF from a browser.

## Submission (Google Classroom)
You must submit **two items**:
1) A **PDF technical report** (exported from `report/technical_report.md` or from the notebook)
2) The **functional repository** (either as a zipped folder or a GitHub link)

Recommended submission checklist:
- PDF: `report/technical_report.pdf` (generate from the Markdown report)
- Repo: ZIP of the repo (exclude `.venv/`) or paste the GitHub repository link
- Optional: attach `outputs/summary_tables.xlsx` if your lecturer wants an Excel workbook directly

To submit:
1. Open the assignment link in Google Classroom.
2. Click the assignment → **View assignment**.
3. Under **Your work**, click **Add or create**.
4. Upload the PDF report, and either upload the ZIP repository or add the GitHub link.
5. Click **Turn in / Submit**.
