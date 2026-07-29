# Time Series Econometrics — Modelling and Forecasting the Indian Government Bond Yield Curve

## Overview
Analysis of Indian G-Sec yields (2016–2025) across the 1-year, 5-year, and 10-year tenors, with a focus on yield curve dynamics, their relationship to the RBI repo rate, and short-horizon forecasting.

## Data
- **Yield data**: RBI DBIE, "Yield of SGL Transactions in Government Dated Securities for Various Maturities"
- **Repo rate**: monthly series
- Note: raw data files are not included in this repo (see `.gitignore`) — see the "Data" section below for how to source them, or add a `sample_data/` folder with a small illustrative extract.

## Methodology
1. **Data cleaning** — reshaping, indexing by date, aligning yield and repo series on a common date range
2. **Yield curve statistics** — 10yr–1yr spread, descriptive stats
3. **Repo rate vs. yields** — correlation analysis
4. **Stationarity testing** — Augmented Dickey-Fuller test on levels and first differences
5. **Model identification** — ACF/PACF plots to select ARIMA order
6. **Forecasting** — ARIMA(1,1,1) fit on the 10-year yield, train/test split, forecast accuracy (MAE, RMSE, MAPE)
7. **Future forecast** — 12-month ahead projection using the full sample

## Repository Structure
```
├── notebooks/
│   └── bond_yield_curve_analysis.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## Setup
```bash
pip install -r requirements.txt
```

## Key Results
- *(fill in: average spread, ADF test conclusion, chosen ARIMA order, forecast accuracy metrics)*

## Author
Shivani — M.A.Economics (Applied Quantitative Finance), Madras School of Economics
