# ARIMA Model

**ARIMA** stands for AutoRegressive Integrated Moving Average. It is a popular statistical method for time series forecasting.

#### Simple Explanation

Think of ARIMA as a weather forecaster that looks at patterns of pressure, temperature, and wind speed (past values) to predict the weather (future values). In time series language, ARIMA considers past values (auto-regressive part), trends and seasonality (integrated part), and random shocks (moving average part) to forecast future data points.

#### Formula

The ARIMA model is represented by three terms: AR(p), I(d), and MA(q), where:

- **AR(p)** is the auto-regressive part with `p` indicating the number of lag observations included in the model.
- **I(d)** is the integrated part, where `d` is the order of differencing required to make the time series stationary.
- **MA(q)** is the moving average part with `q` indicating the size of the moving average window.

The ARIMA model can be formulated as:
```math
(1 - Σ[αₚ * B^p]) (1 - B)^d Yₜ = (1 + Σ[θₑ * B^q]) εₜ
```
where:

- `Yₜ` is the time series.
- `B` is the backshift operator.
- `αₚ` are the parameters for the AR part.
- `θₑ` are the parameters for the MA part.
- `εₜ` is white noise.

#### Parameters

- `p`: The number of lag observations in the model.
- `d`: The degree of differencing.
- `q`: The size of the moving average window.

#### Feature Importance

In ARIMA, feature importance isn't discussed in the same way as it is for algorithms like decision trees. Instead, the focus is on the significance of the parameters (`αₚ`, `θₑ`) and the lagged values of the time series.

#### Code

To see how we implemented ARIMA in our project including cross-validation, check out the [ARIMA notebook](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Models/ARIMA/Cycle-2/Combined-Log-Transformed/arima-1.ipynb){target=_blank}.

#### Additional Notes

- ARIMA models are fitted to time series data either to better understand the data or to predict future points in the series (forecasting).
- Seasonal ARIMA (SARIMA) is an extension of ARIMA that explicitly supports univariate time series data with a seasonal component.

To learn more about ARIMA and its applications, check out the [ARIMA documentation](https://otexts.com/fpp3/arima.html){target=_blank}.
