## Data Overview

The datasets powering our oil price prediction models have been carefully curated, stemming from reliable sources and kindly provided by our sponsor. Our primary data channels revolve around historical oil prices, accompanied by significant macroeconomic indicators that potentially influence oil market dynamics.

### Data Sources

**Macroeconomic Data.csv**: This dataset features macroeconomic indicators spanning from January 1986 to June 2023. This comprehensive collection offers a deeper understanding of economic parameters that may have had an impact on oil price trends over the years.

**RWTCm.xls**: This file houses data specific to the Cushing, OK WTI Spot Price FOB (Dollars per Barrel). It encompasses a timeframe from January 1986 up until July 2023.

### Data Integrity

The datasets have been generously provided by our 'sponsor,' a distinguished professor in the Economics department of our school. While the data is thorough and well-researched, it's crucial to note that our datasets aren't regularly updated, primarily because they serve the educational motives of this academic project.

### Data Preprocessing

In ensuring the reliability of our predictions, we followed strict guidelines for data preprocessing. The requirements given to us necessitated certain transformations to ensure the data was in the right state for analysis and modeling. Here are the steps we took:

- #### Nominal to Real Oil Price Conversion

    The provided dataset has the oil price in nominal terms, which isn't adjusted for inflation. To extract more meaningful insights that reflect true market dynamics, we converted the nominal oil prices to real prices using the following formula:


```math 
Real Price = Nominal Price/CPI × 100
```
Where:

- **Nominal Price**: The original oil price as provided in the dataset (before inflation adjustment).

- **CPI (Consumer Price Index)**: This reflects the average change over time in the prices paid by consumers. In our dataset, CPI (All items) is represented by the variable `CPIAUCSL` in the macroeconomic data.
This transformation ensured that the price of oil is **adjusted for inflation**, offering a clearer picture of the market dynamics.

### Log Transformation of Macroeconomic Variables

Due to the significant variation in the macroeconomic data on a relative scale, a log transformation was applied to all the variables, with exceptions:

- Variables expressed in percentages, our client instructed us to consider the following **18** variables as percentages:
  - `UNRATE`, `FEDFUNDS`, `CP3Mx`, `TB3MS`, `TB6MS`, `GS1`, `GS5`, `GS10`, `AAA`, `BAA`, `COMPAPFF`, `TB3SMFFM`, `TB6SMFFM`, `T1YFFM`, `T5YFFM`, `T10YFFM`, `AAAFFM`, `BAAFFM`
  - For more information on what exactly any of these variables represent, please refer to the [Macroeconomic Data Dictionary](variables.md){:target="_blank"} and search accordingly.


- The log transformation, denoted as
log(x), helps in stabilizing variance and making the data more amenable to modeling.

#### What is a Log Transformation?
 - A log transformation is a process where you take the logarithm of the values in your dataset. This is often done in data analysis to deal with skewed data or to make patterns more visible.

!!! info

       For this project, we used log(x) *base 2* initially (Cycle 1) but transitioned to log(x) *base e* (`numpy` default) for Cycle 2. The base doesn't matter as long as it's consistent across all variables.

#### Why Add a Small Constant Before Log Transformation?
- You can't take the logarithm of zero because it's undefined. To avoid this problem, you add a very small number to all your values so that none of them are zero anymore.

#### How Small Should the Constant Be?
- The constant should be smaller than any other value in your dataset. This way, it doesn't change your data much; it just makes sure you don't have any zeros.

#### Our Dataset
- Based on the smallest values we've found in our dataset (after log transformation), which are all larger than 1 (like 11.367264, 11.453453, etc.), adding a tiny number like 0.000001 (which is what 1e-6 is) won't really change those numbers in any meaningful way. It's like adding a drop of water to a swimming pool—it doesn't change the amount of water in the pool in a *way you'd notice*.

##### In Simple Steps:
1. **Check Your Data**: We looked at our data and found the smallest numbers are all much bigger than zero (*not including blank values or negative values, which we'll deal with later*).

2. **Choose a Constant**: We've chosen `1e-6` because it's much smaller than our smallest data point, which in our case was `11.367264`.

3. **Apply the Transformation**: We add this tiny number to all our data points so none are zero, and then take the logarithm of all these slightly adjusted numbers.

4. **Result**: Now all data points have been transformed, and we can use them in our analysis without worrying about the problems that come with taking the logarithm of zero.

So, in this case, using `1e-6` is perfectly fine because it's so small compared to our actual data that it won't really affect our analysis, but it will allow us to perform the log transformation without any issues.


### Dataset Versions

- **Combined Raw (Macroeconomic Data + Oil Price from RWT)**: This is the raw dataset of Macroeconomic Data.csv and RWTCm.xls combined. It's the original dataset as provided to us, with no transformations applied or Real Oil Price calculated using the CPI.
    - Negatives: 1022
    - Zeros: 46
    - Blanks: 90
    - Rows: 450
    - Columns: 128 (including date)
    - Variables: 127 (not including date)
    - Dropped Variables: 0
    - Dates: 1986-01 - 2023-06
    - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/Original/Macroeconomic%20Data.csv){:target="_blank"}

- **Combined CPI Adjusted**: This is still the raw dataset of Macroeconomic Data.csv and RWTCm.xls combined, but with the CPI adjustment applied to the oil price.
    - Negatives: 1022
    - Zeros: 46
    - Blanks: 90
    - Rows: 450
    - Columns: 128 (including date)
    - Variables: 127 (not including date)
    - Dropped Variables: 0
    - Dates: 1986-01 - 2023-06
    - Source: [See here](){:target="_blank"}


- **Combined Log Transformed**: The dataset with a log transformation applied to all applicable variables, *including real oil prices*.
    - Negatives: 2281
    - Zeros: 36
    - Blanks: 199
    - Rows: 450
    - Columns: 128 (including date)
    - Variables: 127 (not including date)
    - Dropped Variables: 0
    - Dates: 1986-01 - 2023-06
    - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/macro_features_and_real_oil_prices_log_tranferred_dropped_Nan_skipped_neg_and_zeros_for_log.csv){:target="_blank"}

- **Combined Log Transformed Excl Roil**: Similar to the previous dataset (Combined Log Transformed) but excludes the log transformation on real oil prices.
    - Negatives: 2281
    - Zeros: 36
    - Blanks: 199
    - Rows: 450
    - Columns: 128 (including date)
    - Variables: 127 (not including date)
    - Dropped Variables: 0
    - Dates: 1986-01 - 2023-06
    - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/cleaned_dataset.csv){:target="_blank"}

- **Combined Log Clean**: This dataset is derived from `Combined_Log_Transformed.csv` with all blanks removed.
  - Negatives: 1454
  - Zeros: 34
  - Blanks: 0
  - Rows: 303 (147 rows removed)
  - Columns: 128 (including date)
  - Variables: 127 (not including date)
  - Dropped Variables: 0
  - Dates: 1992-02 - 2023-03
  - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/cleaned_dataset.csv){:target="_blank"}

- **Combined Log Excl Roil Clean**: This dataset originates from `Combined_Log_Transformed_Excl_Roil.csv` with all blanks removed.
  - Negatives: 1454
  - Zeros: 34
  - Blanks: 0
  - Rows: 303 (147 rows removed)
  - Columns: 128 (including date)
  - Variables: 127 (not including date)
  - Dropped Variables: 0
  - Dates: 1992-02 - 2023-03
  - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/cleaned_dataset.csv){:target="_blank"}

- **Combined Log Excl Roil Clean NoNeg**: An extension of `Combined_Log_Excl_Roil_Clean.csv`, it excludes rows with negative values and drops columns with predominantly negative data.
  - Negatives: 0
  - Zeros: 6
  - Blanks: 0
  - Rows: 97 (206 rows removed)
  - Columns: 124 (including date)
  - Variables: 123 (not including date)
  - Dropped Variables: 4
  - Dates: 1992-03 - 2019-02
  - Source: [See here](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Data/cleaned_dataset.csv){:target="_blank"}

### Data Usage

It's essential to understand that while our datasets are extensive and informative, they are primarily tailored for educational purposes within the context of our current project. We advise users to approach the data with a discerning lens, acknowledging its scope and potential limitations.