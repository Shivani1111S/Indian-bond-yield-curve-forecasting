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
- average spread of the yield curve (10yr - 1yr): 0.93%
- ADF test conclusion:Stationarity test(ADF Test)
Null Hypothesis: Series has a unit root (non-stationary)
If p-value < 0.05: Reject null - series is stationary
If p-value > 0.05:Fail to reject null - series is not stationary
ADF Statistics:-2.4513
p-value:0.1278
conclusion:Non-Stationary

After differencing:
ADF Statistics:-3.9450
p-value:0.0017
conclusion:Stationary 
- chosen ARIMA order: (1,1,1)
- forecast accuracy metrics: 
MAE  (Mean Absolute Error): 0.44%
RMSE (Root Mean Square Error): 0.51%
MAPE (Mean Absolute Percentage Error): 6.65%

## Author
Shivani — M.A.Economics (Applied Quantitative Finance), Madras School of Economics
