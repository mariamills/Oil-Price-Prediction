# Model Performance on Various Datasets

The results provided show the performance of several models on various datasets, with metrics such as __Mean Absolute Error (MAE)__, __Mean Squared Error (MSE)__, __Root Mean Squared Error (RMSE)__, __Mean Absolute Percentage Error (MAPE)__, and the __coefficient of determination (R^2)__. <br>

Here's a breakdown of what these results suggest for each model:

## Naive Forecast (Baseline)

The Naive Forecast model, which predicts future values based on the most recent data point, has been evaluated across various datasets.<br>
Here's a breakdown of its performance:

- __Combined_Raw.csv:__

    - __MAE__: `3.09`, __MSE__: `22.14`, __RMSE__: `4.71`, __MAPE__: `6.99%`, __R^2__: `0.975`
    - This dataset shows a relatively high accuracy with an R^2 of 0.975, indicating the model can explain 97.5% of the variance in the data.

- __Combined_CPI_Adjusted.csv:__

    - __MAE__: `1.46`, __MSE__: `4.42`, __RMSE__: `2.10`, __MAPE__: `6.89%`, __R^2__: `0.963`
    - The model performs well, with a high R^2 value, suggesting good predictive capability.

- __Combined_Log_Transformed.csv:__

    - __MAE__: `0.068`, __MSE__: `0.009`, __RMSE__: `0.097`, __MAPE__: `2.36%`, __R^2__: `0.956`
    - Excellent performance with low error metrics and a high R^2, indicating strong predictive accuracy.

- __Combined_Log_Clean.csv:__

    - __MAE__: `0.068`, __MSE__: `0.010`, __RMSE__: `0.101`, __MAPE__: `2.32%`, __R^2__: `0.951`
    - Similar to the log-transformed dataset, showing high accuracy and low error rates.

- __Combined_Log_Clean_NoNeg.csv:__

    - __MAE__: `0.087`, __MSE__: `0.019`, __RMSE__: `0.137`, __MAPE__: `2.99%`, __R^2__: `0.889`
    - Slightly lower performance compared to other log-transformed datasets but still shows good predictive capability.

- __Combined_Log_Transformed_Excl_Roil.csv:__

    - __MAE__: `1.46`, __MSE__: `4.42`, __RMSE__: `2.10`, __MAPE__: `6.89%`, __R^2__: `0.963`
    - Performance is identical to the CPI-adjusted dataset, indicating consistent model behavior across these datasets.

- __Combined_Log_Excl_Roil_Clean.csv:__

    - __MAE__: `1.55`, __MSE__: `5.93`, __RMSE__: `2.44`, __MAPE__: `7.04%`, __R^2__: `0.949`
    - Shows good predictive accuracy, though slightly lower than the CPI-adjusted and log-transformed datasets.

- __Combined_Log_Excl_Roil_Clean_NoNeg.csv__

    - __MAE__: `1.79`, __MSE__: `8.64`, __RMSE__: `2.94`, __MAPE__: `8.98%`, __R^2__: `0.883`
    - This dataset shows the lowest performance among the evaluated datasets, but still maintains a decent level of predictive accuracy.

### 'Best' Dataset:

For the Naive Forecast model, the dataset that yielded the 'best' results is the `Combined_Log_Transformed.csv`.

The Naive Forecast model demonstrates strong performance across various datasets, particularly with log-transformed data, where it achieves high R^2 values and low error metrics.

This suggests that the most recent data point is often a good predictor for the next, especially in datasets where logarithmic transformations have been applied, indicating a level of consistency or trend in the data.<br>
However, it's important to note that while the Naive Forecast can be surprisingly effective, it's a simple approach that doesn't account for complex patterns or potential changes in trends.

## Random Forest

- __Datasets with NaNs__: We've chosen not to use Random Forest on the following datasets: `Combined_Raw.csv`, `Combined_CPI_Adjusted.csv`, and `Combined_Log_Transformed.csv` due to containing *NaN values*. <br> 
__Random Forest cannot handle NaNs__; they need to be imputed or the rows/columns with NaNs must be dropped before modeling.

- __Combined_Log_Clean.csv__:

    - __MAE__: `0.085`, __MSE__: `0.016`, __RMSE__: `0.126`, __MAPE__: `3.01%`, __R^2__: `0.92`
    - The Random Forest model shows strong performance on the cleaned log-transformed dataset. The high R^2 score indicates that the model explains a significant portion of the variance in the data.

- Combined_Log_Clean_NoNeg.csv:
    - __MAE__: `0.043`, __MSE__: `0.003`, __RMSE__: `0.058`, __MAPE__: `1.55%`, __R^2__: `0.98`
    - This dataset yields the best performance for Random Forest, with very low error metrics and a high R^2 score. Removing negative values seems to have a positive impact on the model's accuracy.

- __Combined_Log_Excl_Roil_Clean.csv__:
    - __MAE__: `1.70`, __MSE__: `5.88`, __RMSE__: `2.43`, __MAPE__: `9.00%`, __R^2__: `0.94`
    - While the performance is strong, the errors are higher compared to the datasets where the real oil price is included and log-transformed. This suggests that including real oil data helps improve the model's predictions.

- Combined_Log_Excl_Roil_Clean_NoNeg.csv:

    - __MAE__: `0.80`, __MSE__: `0.95`, __RMSE__: `0.98`, __MAPE__: `4.25%`, __R^2__: `0.99`
    - This dataset shows excellent performance with the highest R^2 score among the datasets where real oil price is excluded from log transformation. The low error metrics indicate a highly accurate model.

#### 'Best' Dataset:

The Random Forest model performs exceptionally well on datasets that have undergone log transformation and cleaning, especially when negative values are removed.<br>
The inclusion of real oil price data, when log-transformed, appears to significantly enhance the model's predictive capabilities.

The MAPE values are consistently low across datasets where the model is applied, indicating that the predictions are, on average, very close to the actual values.<br>
The high R^2 scores, particularly for the `Combined_Log_Clean_NoNeg.csv` and `Combined_Log_Excl_Roil_Clean_NoNeg.csv` datasets, demonstrate the model's effectiveness in capturing the variance in the data.

These results underscore the importance of data preprocessing and feature selection in building effective predictive models. The Random Forest algorithm, in particular, benefits from cleaner data (free from NaNs and negative values) and appropriate transformations, leading to more accurate predictions.<br>
It's crucial to ensure that these models are not __overfitting__ the training data, which can be verified through cross-validation or by evaluating the model's performance on a separate test set.


## XGBoost

The results provided showcases the performance of the XGBoost regression model across various datasets, evaluated using metrics such as __Mean Absolute Error (MAE)__, __Mean Squared Error (MSE)__, __Root Mean Squared Error (RMSE), Mean Absolute Percentage Error (MAPE)__, and the __coefficient of determination (R^2)__.<br>
Here's an analysis of the results:

- __Combined_Raw.csv__:

    - __MAE__: `2.72`, __MSE__: `14.92`, __RMSE__: `3.86`, __MAPE__: `6.41%`, __R^2__: `0.98`
    - This dataset shows excellent performance with a very high __R^2__ score, indicating that the model explains a significant portion of the variance in the data. The errors are relatively low, suggesting good predictive accuracy.

- __Combined_CPI_Adjusted.csv__:
  
    - __MAE__: `1.57`, __MSE__: `4.73`, __RMSE__: `2.17`, __MAPE__: `7.58%`, __R^2__: `0.95`
    - The model performs well on this dataset too, with a high __R^2__ score. The errors are slightly higher compared to the raw dataset, which might be due to the CPI adjustment affecting the data's characteristics. 

- __Combined_Log_Transformed.csv__:

    - __MAE__: `0.07`, __MSE__: `0.01`, __RMSE__: `0.10`, __MAPE__: `2.53%`, __R^2__: `0.94`
    - The logarithmic transformation seems to have significantly improved the model's performance, with very low error metrics and a high __R^2__ score. This indicates that the log transformation helps in linearizing the relationships in the data.

- __Combined_Log_Clean.csv__:

    - __MAE__: `0.08`, __MSE__: `0.01`, __RMSE__: `0.12`, __MAPE__: `2.88%`, __R^2__: `0.93`
    - Cleaning the data post-log transformation maintains strong model performance, although there's a slight increase in errors and a minor decrease in __R^2__ compared to the non-cleaned log-transformed data.

- __Combined_Log_Clean_NoNeg.csv__:

    - __MAE__: `0.05`, __MSE__: `0.004`, __RMSE__: `0.07`, __MAPE__: `1.81%`, __R^2__: `0.97`
    - Removing negative values further enhances model performance, resulting in the lowest errors and a very high __R^2__ score among all datasets. This suggests that negative values _might_ have been outliers or noise in the data.

- __Combined_Log_Transformed_Excl_Roil.csv__:

    - __MAE__: `1.48`, __MSE__: `4.12`, __RMSE__: `2.03`, __MAPE__: `7.10%`, __R^2__: `0.96`
    - Excluding the real oil price from the log transformation results in increased errors and a slightly lower __R^2__ score compared to the full log-transformed dataset. This indicates that the real oil price contributes significantly to the model's predictive power.

- __Combined_Log_Excl_Roil_Clean.csv__:

    - __MAE__: `1.60`, __MSE__: `4.12`, __RMSE__: `2.03`, __MAPE__: `8.01%`, __R^2__: `0.96`
    - Cleaning the dataset while excluding real oil price from log transformation shows similar performance to the non-cleaned version, with a slight increase in __MAPE__.

- __Combined_Log_Excl_Roil_Clean_NoNeg.csv__:

    - __MAE__: `1.14`, __MSE__: `2.04`, __RMSE__: `1.43`, __MAPE__: `6.18%`, __R^2__: `0.97`
    - This dataset, after excluding the real oil price from the log transformation and cleaning negative values, shows impressive performance. The __R^2__ score of `0.97` indicates that the model explains a vast majority of the variance in the dataset. The errors (MAE, MSE, RMSE) are relatively low, and the __MAPE__ of `6.18%` suggests that the predictions are, on average, within about `6.18%` of the actual values, which is quite accurate for forecasting tasks.


#### 'Best' Dataset:

The `Combined_Log_Clean_NoNeg.csv` dataset generally shows the best performance across most metrics, highlighting the effectiveness of log transformation and cleaning negative values in the data.

The inclusion of the real oil price in the log transformation appears to be crucial for model performance, as seen in the datasets where it's excluded.

## Polynomial Regression

- __Datasets with NaNs__: We've chosen not to use Polynomial Regression on the following datasets: `Combined_Raw.csv`, `Combined_CPI_Adjusted.csv`, and `Combined_Log_Transformed.csv` due to containing *NaN values*. <br>
  __Polynomial Regression cannot handle NaNs__; they need to be imputed or the rows/columns with NaNs must be dropped before modeling.

- __Combined_Log_Clean.csv__:
    - __MAE__: `0.10`, __MSE__: `0.017`, __RMSE__: `0.129`, __MAPE__: `3.44%`, __R^2__: `0.92`
    - This dataset, with log transformation and cleaning, shows strong performance in the polynomial regression model. The __R^2__ score of `0.92` is quite high, indicating that the model explains a significant portion of the variance in the data. The error metrics are low, and a __MAPE__ of `3.44%` suggests good accuracy.

- __Combined_Log_Clean_NoNeg.csv__:
   
    - __MAE__: `0.094`, __MSE__: `0.014`, __RMSE__: `0.119`, __MAPE__: `3.30%`, __R^2__: `0.92`
    - Similar to the previous dataset, this one also shows strong performance. The removal of negative values seems to have a slightly positive impact on the model's accuracy, as indicated by the marginally lower error metrics and MAPE.

- __Combined_Log_Excl_Roil_Clean.csv__:

    - __MAE__: `2.43`, __MSE__: `11.78`, __RMSE__: `3.43`, __MAPE__: `14.26%`, __R^2__: `0.89`
    - In this dataset, where the real oil price is included but not log-transformed, the model's performance drops compared to the previous two datasets. The errors are significantly higher, and the R^2 score, while still good, is lower. _This suggests that the log transformation of the real oil price is beneficial for the model's performance_.

- __Combined_Log_Excl_Roil_Clean_NoNeg.csv__:
   
    - __MAE__: `1.73`, __MSE__: `5.03`, __RMSE__: `2.24`, __MAPE__: `10.01%`, __R^2__: `0.93`
    - This dataset, which excludes the real oil price from log transformation and cleans negative values, shows improved performance compared to the previous dataset but is still not as strong as when the real oil price is log-transformed. The R^2 score is high, but the error metrics, especially MAPE, are higher than in the first two datasets.

### 'Best' Dataset:

The `Combined_Log_Clean.csv` and `Combined_Log_Clean_NoNeg.csv` datasets yield the best results with the Polynomial Regression model, indicating that log transformation and cleaning of the data are crucial for model performance.

Excluding the real oil price from log transformation (while still including it in the dataset) leads to a decrease in model performance, suggesting that the way this feature is processed has a significant impact.
The relatively high R^2 scores across all datasets indicate that Polynomial Regression is a suitable model for this type of data, but the choice of data preprocessing steps (like log transformation and cleaning of negatives) plays a crucial role in achieving optimal performance.

As with any model, it's important to validate these results on unseen data to ensure that the model generalizes well and is not overfitting.

## ARIMA

- __Combined_Raw.csv__:

    - __MAE__: `16.80`, __MSE__: `522.13`, __RMSE__: `22.85`, __MAPE__: `25.48%`, __R^2__: `-0.49`
    - The ARIMA model performs __poorly__ on the raw dataset, as indicated by high error metrics and a negative R^2 score. This suggests that the model is not suitable for the raw data without preprocessing.

- Combined_CPI_Adjusted.csv:

    - __MAE__: `4.47`, __MSE__: `36.84`, __RMSE__: `6.07`, __MAPE__: `20.41%`, __R^2__: `-0.10`
    - Although the error metrics are lower compared to the raw dataset, the negative R^2 score still indicates poor model performance. This suggests that CPI adjustment alone is not sufficient for the ARIMA model to perform well.

- __Combined_Log_Transformed.csv__:
   
    - __MAE__: `0.21`, __MSE__: `0.081`, __RMSE__: `0.285`, __MAPE__: `7.06%`, __R^2__: `-0.05`
    - The log transformation improves the model's performance significantly, as seen in the lower error metrics. However, the slightly negative R^2 score suggests that the model still does not fit the data well.

- __Combined_Log_Clean.csv__:
   
     - __MAE__: `0.28`, __MSE__: `0.106`, __RMSE__: `0.326`, __MAPE__: `8.76%`, __R^2__: `-0.58`
     - Despite cleaning the data, the ARIMA model's performance does not improve significantly. The negative R^2 score indicates a poor fit to the data.

- __Combined_Log_Clean_NoNeg.csv__:

    - __MAE__: `0.23`, __MSE__: `0.112`, __RMSE__: `0.334`, __MAPE__: `7.62%`, __R^2__: `-0.22`
    - Removing negative values does not lead to a substantial improvement in model performance. The negative R^2 score persists, indicating a poor fit.

- __Combined_Log_Transformed_Excl_Roil.csv__:

    - __MAE__: `4.47`, __MSE__: `36.84`, __RMSE__: `6.07`, __MAPE__: `20.41%`, __R^2__: `-0.10`
    - Similar to the Combined_CPI_Adjusted.csv dataset, the performance here is poor, with a negative R^2 score, suggesting that excluding real oil price from log transformation does not benefit the ARIMA model.

- __Combined_Log_Excl_Roil_Clean.csv__:

    - __MAE__: `6.27`, __MSE__: `58.57`, __RMSE__: `7.65`, __MAPE__: `24.66%`, __R^2__: `-0.68`
    - This dataset shows one of the worst performances, with high error metrics and a significantly negative R^2 score, indicating a very poor fit.

- __Combined_Log_Excl_Roil_Clean_NoNeg.csv__:

    - __MAE__: `6.19`, __MSE__: `69.51`, __RMSE__: `8.34`, __MAPE__: `29.55%`, __R^2__: `-0.17`
    - Despite cleaning and removing negative values, the performance remains poor, as indicated by high error metrics and a negative R^2 score.

### 'Best' Dataset:

The ARIMA model generally performs __poorly across all datasets, with negative R^2 scores in most cases__, indicating that it is not a suitable model for this type of data.

The log-transformed datasets show relatively better performance compared to others, but the improvement is not enough to make the ARIMA model competitive with other models like XGBoost or Polynomial Regression.

_The consistently negative R^2 scores across different datasets suggest that ARIMA struggles to capture the underlying patterns in this data, possibly due to its non-stationary nature or complex relationships that ARIMA cannot model effectively._<br>
These results highlight the importance of choosing the right model for the data at hand and the limitations of ARIMA in handling complex datasets like these.

#### Why  ARIMA may not be suitable for this data?

ARIMA (AutoRegressive Integrated Moving Average) models might not perform well on certain datasets due to a few key reasons:

1. __Non-Stationary Data__: ARIMA models are designed for stationary time series, where the statistical properties like mean and variance are constant over time. If the data shows trends or seasonality, it needs to be transformed into a stationary form before using ARIMA, _which might not always be effective_.

2. __Complex Relationships__: ARIMA models may struggle with data that has complex, non-linear relationships. They are fundamentally linear models and might not capture complex patterns present in some datasets, especially those influenced by numerous external factors.

3. __Lack of External Factors__: ARIMA models primarily focus on the time series data itself and do not incorporate external variables or factors. If the dataset is influenced by external factors (__like economic indicators, global events, etc.__), ARIMA might not be able to account for these influences.

4. __Overfitting on Noisy Data__: ARIMA can overfit on noisy data, leading to a model that performs well on training data but poorly on unseen data. This is particularly problematic if the noise in the data is random and does not contain information about future values.

5. __Parameter Selection__: Choosing the right parameters (p, d, q) for ARIMA models can be challenging. Incorrect parameter choices can lead to poor model performance.

In summary, ARIMA's limitations in handling non-stationary data, complex relationships, external factors, and its sensitivity to parameter selection and noisy data can contribute to its suboptimal performance on certain datasets.

## Prophet

- __Combined_Raw.csv__: This dataset contains the raw data without any preprocessing. The model's performance is moderate with an __R^2__ of `0.72`. However, the error metrics like __MAE__ and __RMSE__ are relatively high, suggesting that the raw data might have outliers or noise affecting the model's predictions.

- __Combined_CPI_Adjusted.csv__: Adjusting for CPI helps in normalizing the data related to inflation or other economic changes over time. The model shows a decent fit with an __R^2__ of `0.66`, but the error metrics are still on the higher side.

- __Combined_Log_Transformed.csv__: Log transformation helps in stabilizing the variance and making the data more _'model-friendly'_. This dataset shows significant improvement in all metrics, especially in reducing the __MAPE__ to `6.19%` and achieving an __R^2__ of `0.73.`

- __Combined_Log_Clean.csv__: Further cleaning the log-transformed data results in slightly better performance, indicating that removing anomalies or irrelevant data points can enhance model accuracy.

- __Combined_Log_Clean_NoNeg.csv__: This dataset yields the best performance across all metrics, with the lowest errors and the highest __R^2__ of `0.77`. Removing negative values seems to have a substantial positive impact, suggesting that such values might have been outliers or noise.

- __Combined_Log_Transformed_Excl_Roil.csv__: Excluding real oil data in the log-transformed dataset shows a decrease in model performance compared to when real oil data is included, indicating that real oil prices might be a significant predictor for the model.

- __Combined_Log_Excl_Roil_Clean.csv__ and Combined_Log_Excl_Roil_Clean_NoNeg.csv: These datasets, which exclude real oil data and involve cleaning, show lower performance compared to datasets where real oil data is included. This further emphasizes the importance of real oil prices in the prediction model.


#### 'Best' Dataset:

The `Combined_Log_Clean_NoNeg.csv` dataset stands out as the 'best' performer for the Prophet model. The combination of log transformation, data cleaning, and removal of negative values significantly enhances the model's predictive accuracy. The low __MAPE__ of `5.71%` and the highest __R^2__ of `0.77` suggest that the model's predictions are both accurate and reliable for this dataset.

While the `Combined_Log_Clean_NoNeg.csv` dataset shows the best performance, it's essential to ensure the model's ability to generalize. This can be done by evaluating the model on a separate test set or using time-series cross-validation techniques.


## XGBoost (Time Series)

To be added.