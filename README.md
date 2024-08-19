
# Time Series Analysis Introduction

Welcome to the Time Series Analysis Introduction repository! This project aims to provide a comprehensive introduction to the fundamental concepts and techniques in time series analysis. Below is an overview of the topics covered in this repository and their importance in time series analysis.

## Table of Contents
## Table of Contents
1. [Trend](#trend)
2. [Seasonality](#seasonality)
3. [Noise](#noise)
4. [Seasonal Decomposition](#seasonal-decomposition)
5. [Stationary and Non-Stationary Series](#stationary-and-non-stationary-series)
6. [Dickey-Fuller Test](#dickey-fuller-test)
7. [Differencing](#differencing)
8. [Concept of Lags](#concept-of-lags)
9. [ACF and PACF Plot](#acf-and-pacf-plot)
10. [Auto-Regressive Series](#auto-regressive-series)
11. [Moving Average Series](#moving-average-series)
12. [ARIMA Model](#arima-model)
13. [SARIMA Model](#sarima-model)
14. [Prophet Model](#prophet-model)
15. [Auto ARIMA](#auto-arima)

## Trend
A trend in a time series is a long-term increase or decrease in the data. It is essential to identify trends as they provide insights into the general direction in which the data is moving over time. For instance, in financial markets, recognizing an upward or downward trend can inform investment strategies.

## Seasonality
Seasonality refers to periodic fluctuations in a time series that occur at regular intervals, such as daily, monthly, or yearly. Identifying seasonality helps in understanding recurring patterns and making more accurate forecasts. For example, retail sales often peak during the holiday season, and recognizing this pattern is crucial for inventory management.

## Noise
Noise is the random variation in a time series that cannot be attributed to trends or seasonality. It is crucial to understand and filter out noise to better analyze the underlying patterns in the data. By reducing noise, analysts can make more reliable predictions and decisions.

## Seasonal Decomposition
Seasonal decomposition involves breaking down a time series into its constituent components: trend, seasonality, and noise. This technique helps in isolating and analyzing each component separately. Decomposition provides a clearer understanding of the underlying structure of the data, which is valuable for model building and forecasting.

## Stationary and Non-Stationary Series
A stationary series has constant mean and variance over time, while a non-stationary series does not. Stationarity is a critical assumption in many time series models, making it essential to test and transform non-stationary series. For example, stock prices are often non-stationary, but returns (differences in prices) are typically stationary.

## Dickey-Fuller Test
The Dickey-Fuller test is a statistical test used to determine whether a time series is stationary. It is a vital tool for validating the assumption of stationarity before applying time series models. By confirming stationarity, analysts can ensure the reliability of their models.

## Differencing
Differencing is a technique used to transform a non-stationary series into a stationary one by subtracting the previous observation from the current observation. It is a common method for achieving stationarity. Differencing helps in stabilizing the mean of a time series, making it easier to model and forecast.

## Concept of Lags
Lags refer to the past values in a time series that are used to predict future values. The concept of lags is crucial in time series analysis as it helps in understanding the dependence of current values on past values. For instance, in an Auto-Regressive (AR) model, the value at time `t` depends on the value at time `t-1`, `t-2`, and so on.

## ACF and PACF Plot
Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) plots are used to identify the correlation between observations at different lags. These plots help in determining the appropriate order of AR and MA models.

- **ACF Plot**: Shows the correlation between the time series and its lagged values. If the ACF plot shows significant correlations at specific lags, it indicates that past values have a linear relationship with future values.
- **PACF Plot**: Shows the partial correlation between the time series and its lagged values, controlling for the values of the time series at all shorter lags. Significant correlations in the PACF plot suggest the order of the AR model.

### Identifying AR or MA Models
- **AR Model**: If the PACF plot shows a sharp cutoff after a few lags (indicating significant correlations at those lags), it suggests an AR model. The ACF plot will decay gradually.
- **MA Model**: If the ACF plot shows a sharp cutoff after a few lags, it suggests an MA model. The PACF plot will decay gradually.

## Auto-Regressive Series
An Auto-Regressive (AR) series is a time series model where the current observation is regressed on its previous observations. AR models are useful for capturing the linear dependence in a time series. For example, in weather forecasting, today's temperature might be predicted based on the temperatures of the past few days.

## Moving Average Series
A Moving Average (MA) series is a time series model where the current observation is a linear combination of past error terms. MA models help in capturing the noise structure in a time series. For example, an MA model can be used to smooth out short-term fluctuations in economic data.

## ARIMA Model
The ARIMA (AutoRegressive Integrated Moving Average) model is an extension of the ARMA model that adds an "Integration" component to handle non-stationary data. The model is denoted as ARIMA(p, d, q), where:
- **p**: The number of lag observations in the model (AR component).
- **d**: The number of times that the raw observations are differenced to make the data stationary (Integrated component).
- **q**: The size of the moving average window (MA component).

### When and Where to Use ARIMA
- **Non-Stationary Data**: ARIMA is well-suited for time series data that is non-stationary. Differencing (represented by \( d \)) helps in transforming non-stationary data into a stationary form.
- **Univariate Series**: ARIMA models work best for univariate time series data (data with only one variable over time).
- **Short to Medium-term Forecasting**: It is commonly used for short to medium-term forecasts where the relationships in the data remain consistent over time.

## SARIMA Model
The SARIMA (Seasonal ARIMA) model is an extension of the ARIMA model that explicitly supports seasonality in the data. It adds seasonal components to the ARIMA model, denoted as SARIMA(p, d, q)(P, D, Q, m), where:
- **P, D, Q**: The seasonal counterparts to the non-seasonal ARIMA components.
- **m**: The number of periods in a seasonal cycle (e.g., 12 for monthly data with yearly seasonality).

### When and Where to Use SARIMA
- **Seasonal Data**: SARIMA is ideal when your data exhibits a clear seasonal pattern, such as monthly sales data with yearly seasonality.
- **Handling Complex Seasonality**: SARIMA can handle both non-seasonal and seasonal patterns, making it a powerful tool for more complex time series.
- **Long-term Forecasting**: It is useful for longer-term forecasts where seasonality is an important factor in the model.

## Prophet Model
Prophet is a forecasting tool developed by Facebook that is designed to handle time series data that exhibits strong seasonal effects and includes missing data or outliers. It allows for flexible handling of seasonality, trends, and holidays.

### Key Features:
- **Automatic Seasonality Detection**: Prophet automatically detects and handles yearly, weekly, and daily seasonality.
- **Handling Missing Data**: It gracefully handles missing data and outliers without requiring explicit imputation.
- **Customizable**: You can add holiday effects and custom seasonalities that aren’t captured by the default settings.

### When and Where to Use Prophet
- **Business Forecasting**: Prophet is widely used in business and finance for forecasting tasks, particularly in scenarios with strong seasonality and potential external events like holidays.
- **Data with Outliers**: It is effective in situations where data may contain outliers or missing points, making it robust for real-world applications.
- **Easily Interpretable**: The model is designed to be easy to understand and adjust, making it ideal for use by analysts with varying levels of statistical expertise.

## Auto ARIMA
`auto_arima` is a function from the `pmdarima` library that automates the process of finding the best ARIMA model by searching over a range of possible (p, d, q) values and selecting the model that minimizes a specific information criterion, such as AIC (Akaike Information Criterion) or BIC (Bayesian Information Criterion).

### When and Where to Use Auto ARIMA
- **Model Selection Automation**: `auto_arima` is perfect when you want to automate the process of finding the best ARIMA model for your time series data.
- **Saving Time**: It saves time by automatically trying different configurations and choosing the best model, so you don't have to manually test different combinations of parameters.
- **Non-Expert Users**: This tool is useful for those who may not have deep expertise in time series modeling but still need to build effective models.

