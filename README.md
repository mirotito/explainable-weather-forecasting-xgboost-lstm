# Explainable Multi-Horizon Weather Forecasting

## XGBoost and LSTM for Short-Term Temperature and Humidity Prediction

A machine learning study for short-term weather forecasting using XGBoost and LSTM models. The project was developed as a replication and extension of a research-paper-based forecasting approach, with additional explainability analysis using SHAP and a comparative deep-learning model.

## Overview

The objective of this project is to forecast:

- Temperature
- Relative humidity

across three forecasting horizons:

- 1 hour ahead
- 2 hours ahead
- 3 hours ahead

The study evaluates XGBoost as the primary forecasting model and compares its performance with an LSTM-based time-series model.

The project also incorporates SHAP-based explainability to investigate the influence of individual input features on model predictions.

## Dataset

Weather data was collected through the Open-Meteo API for Cairo, Egypt.

The dataset contains 4,344 hourly observations with the following variables:

- Temperature
- Relative Humidity
- Solar Radiation
- Surface Pressure
- Wind Speed

Model performance was evaluated using:

- R² Score
- Root Mean Squared Error (RMSE)

## Methodology

### 1. Data Preparation

The weather data was processed and transformed into a supervised learning structure suitable for short-term forecasting.

Temporal lag features were incorporated to capture recent weather behaviour and provide historical context to the forecasting models.

### 2. XGBoost Forecasting

XGBoost regression was used as the primary forecasting approach.

The implemented configuration includes:

| Parameter | Value |
|---|---:|
| Estimators | 10,000 |
| Learning Rate | 0.05 |
| Maximum Depth | 5 |

Separate forecasting horizons were evaluated for 1, 2, and 3 hours ahead.

### 3. Explainable AI with SHAP

SHAP was used to analyse model predictions and identify the contribution of individual features.

This provides an additional layer of interpretability beyond predictive accuracy and helps investigate which temporal and environmental variables most strongly influence the model.

### 4. LSTM Comparison

An LSTM model was implemented as a complementary time-series approach.

The LSTM uses the previous 24 hours of:

- Temperature
- Humidity
- Solar Radiation
- Surface Pressure
- Wind Speed

to learn temporal weather patterns and predict future temperature.

The comparison evaluates the trade-offs between predictive performance, interpretability, and computational practicality.

## Results

### Temperature Forecasting — XGBoost

| Forecast Horizon | R² | RMSE |
|---|---:|---:|
| 1 Hour | 0.9757 | 0.8793 |
| 2 Hours | 0.9600 | 1.1291 |
| 3 Hours | 0.9351 | 1.4381 |

The replicated XGBoost model achieved higher R² scores and lower RMSE values than the reference results across the evaluated temperature forecasting horizons.

### Humidity Forecasting — XGBoost

| Forecast Horizon | R² | RMSE |
|---|---:|---:|
| 1 Hour | 0.9867 | 2.5459 |
| 2 Hours | 0.9585 | 4.4930 |
| 3 Hours | 0.9168 | 6.3639 |

The results demonstrate strong short-term humidity forecasting performance, with performance naturally decreasing as the forecasting horizon increases.

## XGBoost vs LSTM

The comparative analysis showed that the LSTM achieved stronger predictive accuracy for the evaluated time-series task, while XGBoost provided advantages in explainability, simplicity, and computational practicality.

This comparison highlights an important engineering trade-off between:

- Predictive performance
- Model interpretability
- Computational efficiency
- Deployment practicality

## Key Contributions

This project extends the original research-paper replication through:

1. Multi-horizon forecasting for 1, 2, and 3 hours ahead
2. Temperature and humidity prediction
3. SHAP-based model explainability
4. LSTM-based time-series comparison
5. Comparative evaluation using R² and RMSE
6. Analysis of model performance and practical trade-offs

## Repository Contents

```text
.
└── weather_forecasting_xgboost_lstm.ipynb
