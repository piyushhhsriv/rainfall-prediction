```markdown
# Rainfall Prediction — Austin Weather

This repository contains a Jupyter Notebook that performs a Rainfall Prediction project using the Austin weather dataset (`austin_weather.csv`).

## Contents
- `rainfall_prediction.ipynb` — Jupyter Notebook with data cleaning, exploratory analysis, Linear Regression model, evaluation and visualizations.
- `austin_weather.csv` — Dataset (place in same directory as the notebook).
- `requirements.txt` — Python packages required to run the notebook.

## Project Summary
- Objective: Predict daily precipitation (PrecipitationSumInches) using weather attributes such as average temperature, humidity, wind speed, visibility, dew point, and sea level pressure.
- Approach:
  - Load dataset and parse dates.
  - Clean the data:
    - Replace trace precipitation values `"T"` with `0.0` (treated as zero here).
    - Convert `-` and blank entries to NaN.
    - Convert numeric columns to numeric dtype and fill missing feature values with medians.
    - Drop rows where the target (precipitation) is missing.
  - Exploratory Data Analysis (time series, correlations, scatterplots).
  - Train/test split and fit a baseline `LinearRegression` model.
  - Evaluate using R², MSE, MAE and plot predicted vs actual precipitation.
- Findings:
  - Precipitation is skewed with many low/zero values; linear regression is a starting baseline.
  - Consider alternative targets (rain/no-rain classification), transforms, or non-linear models for better performance.
  - Additional feature engineering (lags/seasonality) and model tuning recommended.

## How to run
1. Clone or download this repository.
2. Ensure `austin_weather.csv` is in the same folder as the notebook.
3. (Optional) Create and activate a virtual environment.
4. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
5. Launch Jupyter and open `rainfall_prediction.ipynb`:
   ```
   jupyter notebook rainfall_prediction.ipynb
   ```

## Requirements
See `requirements.txt`.

## Next steps / Improvements
- Try classification (rain vs no-rain) using Logistic Regression or tree-based classifiers.
- Use non-linear regressors (RandomForest, Gradient Boosting).
- Add time series features (month, day-of-year, lags) and rolling means.
- Consider different treatments for trace precipitation (`T`) — e.g., a small positive value vs. explicit trace marker.
```
