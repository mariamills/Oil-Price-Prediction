# Prophet Model

**Prophet** is a forecasting tool designed by Facebook for time series data that is especially good at handling data with strong seasonal effects and several seasons of historical data.

#### Simple Explanation

Imagine if you were trying to predict the number of guests who will visit a restaurant every day. You notice patterns like more guests on weekends or on holidays. Prophet is like a smart assistant that helps you account for these regular patterns (seasonality), trends over time (like growth), and special events (like a festival) to predict future attendance.

#### Formula

Prophet models time series data with the following components:
```math
y(t) = g(t) + s(t) + h(t) + e(t)
```
where:

- `y(t)` is the predicted value.
- `g(t)` represents the trend component, modeling non-periodic changes.
- `s(t)` represents periodic changes (weekly, yearly, etc.).
- `h(t)` represents the effects of holidays which can be specified by the user.
- `e(t)` is the error term.

#### Parameters

Prophet does not have traditional model parameters like `p`, `d`, `q` in ARIMA. Instead, it has several adjustable components:

- `growth`: Can be 'linear' or 'logistic' to specify a capacity to which the forecast can grow.
- `seasonality`: Prophet will by default fit weekly and yearly seasonality, if the time series is more than two cycles long.
- `holidays`: You can add custom holidays and events.

#### Feature Importance

Prophet automatically detects and accounts for seasonality, thus there's no traditional feature importance. The model's interpretability comes from the decomposition of the forecast into trend, seasonality, and holiday components.

#### Additional Notes

- Prophet is robust to missing data and shifts in the trend and typically handles outliers well.
- It is also easy to use with intuitive parameters and practices.

For an in-depth understanding and tutorials on Prophet, you can visit the [Prophet documentation](https://facebook.github.io/prophet/docs/quick_start.html){target=_blank}.
