# Airbnb Stock Price Forecasting (Time Series Analysis)

## Overview

This project forecasts monthly Airbnb (ABNB) stock prices using advanced time series forecasting techniques.
It demonstrates end-to-end forecasting — from data preparation and seasonality analysis to model selection, evaluation, and interpretation of forecast accuracy metrics.

## Dataset

- Source: Yahoo Finance – ABNB monthly closing prices
- Period: December 2020 – August 2024
- Frequency: Monthly (aggregated median values)

Before modeling, the data was:

- Checked for stationarity using ADF tests
- Decomposed into trend, seasonal, and residual components
- Visualized to analyze holiday and cyclical patterns in Airbnb’s business
  
## Methodology

| Model                                  | Description                                            |
| -------------------------------------- | ------------------------------------------------------ |
| **Simple Exponential Smoothing (SES)** | Baseline model for level-only data                     |
| **Holt’s Linear Trend Model**          | Captures linear trend without seasonality              |
| **Holt–Winters Additive Model**        | Models both trend and seasonality additively           |
| **Holt–Winters Multiplicative Model**  | Suitable for series with increasing seasonal amplitude |

## Model Comparison


| Metric                                | Purpose                                                                                |
| ------------------------------------- | -------------------------------------------------------------------------------------- |
| **RMSE / MAE / MAPE**                 | Measures absolute and relative forecast errors                                         |
| **MASE (Mean Absolute Scaled Error)** | Compares against a naïve benchmark for scale-free comparison                           |
| **Theil’s U Statistic**               | Evaluates relative forecast efficiency — U < 1 indicates better than naïve forecasting |

## Evaluation Metrics

To rigorously evaluate model accuracy, we used scale-independent and directional accuracy metrics widely recognized in time series analysis:

| Metric                                | Purpose                                                                                |
| ------------------------------------- | -------------------------------------------------------------------------------------- |
| **RMSE / MAE / MAPE**                 | Measures absolute and relative forecast errors                                         |
| **MASE (Mean Absolute Scaled Error)** | Compares against a naïve benchmark for scale-free comparison                           |
| **Theil’s U Statistic**               | Evaluates relative forecast efficiency — U < 1 indicates better than naïve forecasting |

## Key Insights

- Airbnb’s stock exhibits strong seasonal and cyclical behavior, linked to travel seasonality and holidays.
- Additive Holt–Winters successfully captured these patterns while maintaining stability across time horizons.
- Using Theil’s U and MASE highlighted not only accuracy but also forecast efficiency — key for financial time series evaluation.
  
## Installation & Usage

```bash
# 1. Clone the repository
git clone https://github.com/sunny22123/Forecasting---ABNB-stock-price-prediction.git

# 2. Navigate to the project directory
cd Forecasting---ABNB-stock-price-prediction

# 3. Install dependencies
pip install -r requirements.txt

```

## Future Improvements

- Experiment with SARIMA and Prophet for hybrid seasonality modeling.
- Incorporate exogenous features (XREG) such as travel demand and macroeconomic indicators.
- Apply LSTM/Transformer models for long-term nonlinear dynamics comparison.
