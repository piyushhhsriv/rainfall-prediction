# Rainfall Prediction — Austin Weather

This repository contains the Rainfall Prediction project (Module 13). The goal is to predict daily precipitation for Austin, Texas using historical weather data and to explore relationships between precipitation and weather features.

## Repository contents
- `austin_weather.csv` — Raw weather dataset (place in repo root if not present).
- `rainfall_prediction.ipynb` — Jupyter Notebook with data cleaning, EDA, baseline Linear Regression model, evaluation, and visualizations.

## Project overview
1. Data loading and cleaning: handle special tokens such as `T` (trace precipitation), `-`, and missing values; convert appropriate columns to numeric types.
2. Exploratory data analysis: visualize precipitation over time, correlation heatmap, scatter plots between precipitation and predictors (temperature, humidity, wind, etc.).
3. Modeling: baseline Linear Regression (sklearn) to predict `PrecipitationSumInches`; evaluate using R², MSE, MAE.
4. Next steps: try classification (rain/no-rain), feature engineering (lags, rolling means, seasonality), non-linear models (Random Forest, XGBoost), regularization, and cross-validation.

## How to run
1. Ensure `austin_weather.csv` is in the repository root (or adjust the path in the notebook).
2. Install dependencies (recommended in a virtual environment):
```
pip install -r requirements.txt
```
3. Start Jupyter and open the notebook: `jupyter notebook rainfall_prediction.ipynb`.

## Notes on preprocessing choices
- Trace precipitation values `T` were treated as `0.0` in the baseline notebook. Alternative handling (e.g., small non-zero constant or separate flag) can be explored.
- Missing numeric values are filled with medians before training the baseline model.

## Suggested improvements
- Transform the skewed precipitation target (log or use classification).
- Add time-based features (month, day-of-year) and lagged precipitation to capture temporal dependencies.
- Try tree-based models and tune hyperparameters with cross-validation.

## License
This repository is provided for educational purposes. Add a license file if you plan to reuse or distribute the code.