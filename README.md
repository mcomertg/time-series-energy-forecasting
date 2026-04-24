# Time Series Energy Forecasting (ERCOT - Electric Reliability Council of Texas)

- This project builds an end-to-end time series forecasting pipeline for electricity demand using ERCOT (Texas) data from the U.S. Energy Information Administration (EIA).
- The goal is to explore how well statistical models can predict real-world energy demand and compare their performance against operational forecasts.

## Project Structure

- Notebook 01: Data ingestion and validation
- Notebook 02: Exploratory Data Analysis (EDA)
- 03_statistical_forecasting.ipynb: Baseline models, SARIMA modeling, and comparison with EIA forecasts  
- 04_ml_forecasting.ipynb (in progress): Machine learning models using lag and rolling features

## Tech Stack

- Python
- Pandas
- Matplotlib
- scikit-learn
- statsmodels (SARIMA

## Data Source

U.S. Energy Information Administration (EIA) API  
https://api.eia.gov/

Dataset:
- ERCOT electricity demand (Form EIA-930)
- Daily aggregation from hourly data

## Notes

- Data is retrieved via API and not stored in this repository due to size limitations  
- Run **Notebook 01** to fetch and generate datasets locally  
- A missing observation due to daylight saving time (DST) was identified and handled during preprocessing  

---

## Next Steps

- Extend modeling using SARIMAX (exogenous variables) 
- Develop machine learning models (XGBoost)
- Compare statistical vs ML approaches for forecasting performance  
