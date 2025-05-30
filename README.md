
# Time Series Sales Forecasting Project

This repository contains the complete workflow for a **time series sales forecasting project** involving multiple products and cities. The project covers everything from **data cleaning** and **exploratory analysis** to **feature engineering**, **model selection**, **evaluation**, and **forecasting**.

---

## 🚀 Project Overview

The project aims to build reliable forecasts for product sales using time series analysis and machine learning. The dataset contains sales records of three products sold across three cities, with significant data gaps and outliers.

---

## 📊 Project Steps

### 1️⃣ Data Exploration
- Analyzed data imbalance with bar plots.
- Detected and discussed outliers using statistical summaries.

### 2️⃣ Data Cleaning
- Dropped irrelevant columns (e.g., `retail price`).
- Removed erroneous records in `area` and `discounts`.
- Capped outliers using the IQR method.
- Handled missing values with backward filling.
- Calculated sales using:  
  `sales = UnitPrice * (1 - discounts/100) * quantity`
- Standardized dates by removing time zone info and filling date gaps.

### 3️⃣ Feature Engineering
- Created 9 targets (product-city combinations).
- Engineered discount features per product-city.
- Explored sales trends using:
  - Simple Moving Average (SMA)
  - Exponential Moving Average (EMA)
  - Double Exponential Moving Average (DEMA)
  - Triple Exponential Moving Average (TEMA)
- Detected seasonality using periodograms:
  - Weekly, monthly, day-of-week effects.
- Built lag features:
  - Sales lags (1 and 7 days)
  - Discounts lags (2 days).

### 4️⃣ Modeling
- Baseline Models:
  - ARIMA
  - SARIMA
- Machine Learning Models:
  - Linear Regression
  - ElasticNet
  - Random Forest Regressor
  - Gradient Boosting Regressor (GBR)
  - LightGBM
- Model evaluation using MAE and R² metrics.

### 5️⃣ Results and Findings
- DEMA with a 30-day window best captured sales trends.
- Weekly seasonality detected—sales peak on Saturdays and drop on Fridays.
- Final models: XGBoost and LightGBM showed best performance after tuning, though overfitting remained a challenge.
- Forecasted next 10 days using recursive predictions.

---

## 📈 Key Results

| Model       | Training MAE | Testing MAE | Training R² | Testing R² |
|-------------|--------------|-------------|-------------|------------|
| ARIMA       | 188.27       | 178.95      | -0.97       | -0.26      |
| SARIMA      | 279.99       | 211.54      | -4.22       | -0.68      |
| LinReg      | 90.90        | 275.44      | 0.54        | -1.38      |
| ElasticNet  | 93.44        | 206.18      | 0.49        | -0.39      |
| RF          | 40.27        | 166.28      | 0.88        | -0.02      |
| LightGBM    | 26.81        | 161.22      | 0.88        | -0.25      |

---

## 🔍 Conclusions

- Data sparsity and missing records were major challenges.
- Trend and seasonality features significantly improved forecasting accuracy.
- LightGBM and XGBoost models showed the most promise after feature engineering and tuning.
- Hybrid models (e.g., ARIMA + ML) could further enhance forecasting in the future.

---

## 📌 Future Work

- Collect more complete sales data to reduce sparsity and improve model accuracy.
- Explore geographical factors and area-based patterns.
- Experiment with hybrid time series models combining ARIMA and machine learning techniques.
- Investigate marketing campaigns and promotions to explain sales spikes.

---

## 🛠️ Requirements

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- scikit-learn
- xgboost
- lightgbm

---

## 📂 Repository Structure

```
📦 sales-forecasting
 ┣ 📜 README.md
 ┣ 📜 code.ipynb
 ┗ 📜 requirements.txt
```

---

## 📬 Contact

For any questions or discussions, feel free to open an issue or reach out to Mohammed Zien El-abdine mohammed_z_elabdine@hotmail.com.
