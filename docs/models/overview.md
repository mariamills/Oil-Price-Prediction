In our quest to develop an effective machine learning solution for our project, we selected a variety of models, each with unique characteristics and strengths. Our approach was to implement different types of models to understand their performance on our dataset and grasp the nuances of each.

### Cycle 1: Initial Modeling

1. **[XGBoost](xgboost.md){target=_blank}**
   XGBoost, or Extreme Gradient Boosting, was our choice due to its popularity and proven track record in winning Kaggle competitions. It's known for its speed and performance, as well as its ability to handle missing data. We anticipated that XGBoost would provide us with a robust and accurate model, even with the less-than-perfect quality of our initial dataset.

2. **[Random Forest (RF)](random-forest.md){target=_blank}**
   Random Forest was another model we opted for, primarily for its simplicity and effectiveness. It works well for both classification and regression tasks and has the added benefit of feature importance evaluation, which we considered essential for understanding our dataset better. Its ensemble nature, through bootstrapping and averaging predictions, helps in reducing overfitting, making it a reliable choice.

3. **[Polynomial Regression](polynomial-regression.md){target=_blank}**
   We chose Polynomial Regression to provide a contrast to the ensemble methods. It's a type of linear regression that models the relationship between the independent variable x and the dependent variable y as an nth degree polynomial. We were curious to see how a more straightforward, parametric model would perform on our dataset, particularly in capturing any non-linear patterns.

4. **[Naive Forecast (Baseline)](naive.md){target=_blank}**
   To establish a baseline performance, we implemented a Naive Forecasting model. This simple model set the stage for us to better evaluate the performance improvements brought about by the more complex models. It served as a reality check, ensuring that our advanced models were indeed adding value and not just fitting to noise.

### Cycle 2: Time Series Modeling

As we progressed to the second cycle of our project, our focus shifted to time series models, acknowledging the temporal nature of our dataset.

1. **[ARIMA (AutoRegressive Integrated Moving Average)](arima.md){target=_blank}**
   ARIMA is a popular and widely used statistical method for time series forecasting. It captures the underlying patterns and structures in the time series data, making it a suitable choice for our project. We were interested in evaluating how well ARIMA could handle the trends and seasonality in our dataset.

2. **[Prophet](prophet.md){target=_blank}**
   Developed by Facebook, Prophet is specifically designed for forecasting time series data that exhibit strong seasonal patterns. We were drawn to its robustness and ability to handle missing data, as well as its ease of use. Prophet’s ability to provide interpretable parameters was an added bonus, aiding us in understanding the model’s predictions.

3. **[XGBoost (Time Series)](xgboost.md){target=_blank}**
   Given the success of XGBoost in our initial cycle, we decided to adapt it for time series forecasting. We modified the data preparation and feature engineering steps to suit the temporal nature of our data, eager to see if XGBoost’s power could be harnessed in a time series context.

By diversifying our selection of models, we aimed to gain a comprehensive understanding of different approaches to machine learning and time series forecasting. Each model brought its own set of challenges and learnings, contributing to our growing in the field. Through this approach, we not only aimed to achieve the best possible performance on our project but also to equip ourselves with the knowledge and skills that will be invaluable in our future endeavors in data science.