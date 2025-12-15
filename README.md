# Time Series Forecasting for Volatile Financial Assets Using SARIMA

## Executive Summary

Forecasting volatile financial time series is essential for planning, risk management, and scenario analysis, even when precise price prediction is inherently uncertain.

This project demonstrates the application of a Seasonal ARIMA (SARIMA) model to historical Litecoin (LTC/USD) price data to:
- Identify trend and seasonal structures
- Generate short-term forecasts
- Quantify forecast uncertainty using error metrics

The focus of this project is not speculative trading, but the evaluation of classical time series models under high volatility conditions and their suitability for decision support.

## Business & Analytical Problem

Organizations operating in financial markets face significant challenges when forecasting asset prices:

1. **High Volatility** – Sudden price movements driven by external shocks
2. **Seasonality** – Periodic patterns that can distort naïve forecasts
3. **Decision Risk** – Overconfidence in point forecasts can lead to poor decisions

The goal of this project is to assess whether SARIMA can capture meaningful temporal structure in a volatile asset and produce forecasts that are useful for planning and risk-aware decision-making.


## Data Overview

The dataset consists of weekly historical Litecoin (LTC/USD) closing prices from December 2017 to June 2023, sourced from Yahoo Finance.

Each observation includes:
- Date
- Closing exchange rate

Weekly aggregation was chosen to reduce noise while preserving medium-term trends and seasonal effects.


## Data Preparation

- Missing values were assessed and removed where necessary
- Dates were converted to a time-indexed format
- Extreme price movements were examined to distinguish real market events from data errors

Outliers were retained, as they represent genuine market volatility rather than measurement noise.


## Exploratory Time Series Analysis

### Trend & Volatility
The time series exhibits pronounced boom–bust cycles and extended periods of high volatility, typical of cryptocurrency markets.

### Seasonality
Seasonal decomposition revealed recurring patterns in the data, indicating that price behavior is not entirely random and may be influenced by periodic factors.

### Growth Analysis
Annual and monthly growth rates were analyzed to understand the distribution of returns over time rather than focusing solely on price levels.


## Model Selection: SARIMA

SARIMA was selected because it:
- Handles non-stationary data through differencing
- Explicitly models seasonal components
- Provides interpretable parameters for trend and seasonality

While more complex models exist, SARIMA offers transparency and strong baselines for time series forecasting.


## Parameter Selection

Model parameters were selected using the `auto_arima` approach, optimizing for:
- Akaike Information Criterion (AIC)
- Bayesian Information Criterion (BIC)

This ensured a balance between model fit and complexity, reducing the risk of overfitting.


## Model Training & Diagnostics

The SARIMA model was trained on historical data and evaluated through:
- Residual diagnostics to assess remaining autocorrelation
- Distribution checks to validate modeling assumptions

Residual analysis indicated that the model captured the dominant temporal structure in the data.


## Forecasting & Evaluation

The model was used to generate a 90-day forecast horizon.

Performance was evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

Rather than focusing on exact price accuracy, the evaluation emphasizes error magnitude and directional consistency.


## Visualization of Results

Forecasted values were plotted against historical prices to assess alignment with observed trends and seasonal behavior.

The forecasts successfully tracked the general movement of the series while reflecting the inherent uncertainty present in volatile markets.


## Business Value & Use Cases

This forecasting framework can support:

- **Scenario Planning:** Understanding possible future price ranges
- **Risk Management:** Identifying periods of increased uncertainty
- **Benchmarking:** Establishing a baseline model against which advanced methods can be compared
- **Capacity & Exposure Planning:** Informing capital allocation decisions

The model is best suited for short-term planning rather than long-term price prediction.


## Limitations & Future Improvements

- SARIMA assumes linear relationships and may struggle with regime shifts
- External drivers (news, macroeconomic events) are not explicitly modeled
- Future enhancements could include:
  - Prophet for trend flexibility
  - LSTM or Temporal CNNs for non-linear dynamics
  - Exogenous variables (SARIMAX) for improved explanatory power


## Conclusion

This project demonstrates that classical time series models like SARIMA can extract meaningful structure from volatile financial data when applied carefully.

While not suitable for precise price prediction, the model provides valuable insights into trend, seasonality, and forecast uncertainty, making it a useful baseline for financial time series analysis.
