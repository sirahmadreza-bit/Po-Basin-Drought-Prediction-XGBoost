# Po Basin Drought Monitoring & Precipitation Prediction (Jan 2016 - Jun 2026)

An advanced, data-driven machine learning framework to monitor drought dynamics and predict monthly precipitation profiles in the Po River Basin, Italy. This project leverages multi-source data fusion by integrating land-surface satellite observations with dynamic atmospheric thermodynamic parameters over 107 consecutive months.

## 📊 Project Achievements
* **Core Predictive Model:** Hyper-tuned XGBoost Regressor
* **Coefficient of Determination ($R^2$ Score):** `0.54` (Explains 54% of precipitation variance over a complex 10-year timeline)
* **Root Mean Squared Error (RMSE):** `0.03250 m` (~3.2 cm of monthly precipitation error)

## 🔍 Core Implications & Feature Importance
The model successfully maps the **Land-Atmosphere Coupling** and addresses the **Hydrological Lag Effect** in Northern Italy. According to feature importance evaluation:
* **Atmospheric Drivers (55%):** Temperature-Dewpoint Spread (`22%`) and Dewpoint (`21%`) act as primary thermodynamic proxies for moisture saturation.
* **Land Surface Dynamics (37%):** NDVI, NDWI, and their historical time-lags (`Lag1`) reveal that the basin preserves hydrological memory.
* **Climate Baseline (8%):** Seasonality (`Month`) and short-term rainfall memory (`Precip_Lag1`).

### 📌 Feature Importance Weights Evaluation
![Feature Importance](feature_importance.png)

### 📌 Model Performance and Evaluation Plot
![Model Performance](final_plot.png)

## 🛠️ Tech Stack & Data Sources
* **Data Provider:** Google Earth Engine (GEE) API
  * *Satellite Imagery:* `COPERNICUS/S2_SR_HARMONIZED` (Sentinel-2 Surface Reflection at 1km optimized scale reduction)
  * *Climate Reanalysis:* `ECMWF/ERA5_LAND/MONTHLY_AGGR`
* **Core Libraries:** `xgboost`, `scikit-learn`, `pandas`, `numpy`, `ee`, `matplotlib`

## 🚀 How to Run
1. Open the `.ipynb` notebook in Google Colab or Jupyter Notebook.
2. Replace the `PROJECT_ID` variable with your Google Cloud Project ID.
3. Authenticate Earth Engine API and execute the cells sequentially.
