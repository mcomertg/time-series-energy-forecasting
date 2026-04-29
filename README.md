# Time Series Energy Forecasting (ERCOT - Electric Reliability Council of Texas)

This project builds an end-to-end time series forecasting pipeline for electricity demand using ERCOT (Texas) data from the U.S. Energy Information Administration (EIA).

The objective is to evaluate how different modeling approaches perform on real-world energy demand data and compare results against operational forecasts.

---

## Project Overview

This project follows a complete time series workflow:

- Data ingestion from EIA API
- Data validation and preprocessing
- Time series exploratory analysis (trend, seasonality)
- Baseline forecasting models
- Statistical modeling (SARIMA)
- Machine learning forecasting (XGBoost)
- Model evaluation and benchmarking against EIA forecasts

---

## Key Results

- **XGBoost (with net generation)** achieved the best performance  
  → MAPE ≈ **0.63%**

- **EIA forecast (benchmark)**  
  → MAPE ≈ **2.05%**

- **XGBoost (Lag-Based Features Only)**  
  → MAPE ≈ **3.22%**  
  → Represents realistic forecasting without contemporaneous inputs

- **Hybrid Model (Trend + XGBoost)**  
  → MAPE ≈ **7.44%**

- **Linear Trend Model**  
  → MAPE ≈ **11.83%**

---

## Key Insights

- Electricity demand is highly driven by **recent values (lag features)**  
- Machine learning models significantly outperform traditional statistical models when feature engineering is applied  
- Including contemporaneous variables (e.g., net generation) dramatically improves accuracy but may not reflect real forecasting conditions  
- Feature availability has a major impact on forecasting performance  

---

## Project Structure

- **01_ingestion_validation.ipynb**  
  Data ingestion from EIA API, schema validation, and preprocessing  

- **02_eda.ipynb**  
  Time series exploration including trend, seasonality, and data quality checks  

- **03_statistical_forecasting.ipynb**  
  Baseline models, SARIMA modeling, and comparison with EIA forecasts  

- **04_ml_forecasting.ipynb**  
  Machine learning models using lag-based, rolling, and calendar features, including XGBoost and hybrid modeling  

---

## Tech Stack

- Python  
- pandas, numpy  
- matplotlib  
- scikit-learn  
- statsmodels (SARIMA)  
- XGBoost  

---

## Data Source

U.S. Energy Information Administration (EIA) API  
https://api.eia.gov/

Dataset:
- ERCOT electricity demand (Form EIA-930)
- Daily aggregation from hourly data  

---

## Notes

- Data is retrieved via API and not stored in this repository due to size limitations  
- Run **Notebook 01** to fetch and generate datasets locally  
- A daylight saving time (DST) anomaly was identified and handled during preprocessing  

---

## Next Steps

- Incorporate exogenous variables (e.g., weather forecasts)
- Explore hyperparameter tuning for ML models
- Extend to SARIMAX modeling
- Implement experiment tracking and pipeline automation (MLOps)
