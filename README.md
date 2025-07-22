# 📈 Egyptian Population Time Series Analysis

**Authors:**  
- Moustafa El Mahdy
- Malak Gaballa
- Masa Tantawy   

**Date:** May 22, 2023  
**Course Project:** Time Series Analysis  

---
## 📌 Overview

This project focuses on analyzing the historical population growth of Egypt from **1950 to 2023** using **time series modeling techniques**. Our aim was to:

- Understand the population trend.
- Test for stationarity using the Augmented Dickey-Fuller (ADF) test.
- Identify a suitable ARIMA model for forecasting.
- Forecast population values for 2021–2023 and validate them against actuals.

---
## 📂 Dataset

- File: `EG Population TS.csv`
- Format: CSV with two columns: `Year` and `Population`
- Size: 74 observations (from 1950 to 2023)

We trained the model on data from 1950 to 2020 and reserved the last 3 years (2021–2023) for forecasting and evaluation.

---
## 🔍 Methodology

### 1. **Initial Visualization**
- Plotted the raw time series.
- Observed a strong upward trend.

### 2. **Stationarity Check**
- Applied the ADF test with different lag values.
- Determined that the original series is **non-stationary** and **trendless**.

### 3. **Differencing**
- First difference: Still showed signs of a trend.
- Second difference: Made the series **stationary with no trend**.

### 4. **Model Identification**
- Analyzed ACF and PACF plots → ARIMA model suggested.
- Tested multiple ARIMA(p,d,q) configurations:
  - Best model by AIC: **ARIMA(2,2,2)**

### 5. **Model Diagnostics**
- Checked residual assumptions (N.I.C.E):
  - **N**ormality (QQ Plot & Histogram)
  - **I**ndependence (Ljung-Box Test, ACF/PACF)
  - **C**onstant Variance
  - **E**xpectation = 0
- Model M4 (ARIMA(2,2,2)) passed all checks with minor ACF spikes.
- M5 (ARIMA(3,2,2)) used as secondary check but not preferred due to parsimony.

---
## 📦 Tools & Libraries Used

- **R Language**
- `forecast` (for ARIMA modeling)
- `urca` (for unit root tests)
- Base R visualization tools (`plot.ts`, `acf`, `pacf`, `qqnorm`, etc.)

---
## ✅ Key Takeaways

- The Egyptian population shows a consistent upward trend.
- ARIMA(2,2,2) effectively models and forecasts the population.
- Forecasting accuracy remains high for near-future predictions.
- Stationarity and model assumptions are essential for reliable time series analysis.

