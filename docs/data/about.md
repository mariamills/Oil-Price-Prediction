# Overview

The datasets powering our oil price prediction models have been carefully curated, stemming from reliable sources. Our primary data channels revolve around historical oil prices, accompanied by significant macroeconomic indicators that potentially influence oil market dynamics.

## Data Sources

**Macroeconomic Data.csv**: This dataset features macroeconomic indicators spanning from January 1986 to June 2023. This comprehensive collection offers a deeper understanding of economic parameters that may have had an impact on oil price trends over the years.

**RWTCm.xls**: This file houses data specific to the Cushing, OK WTI Spot Price FOB (Dollars per Barrel). It encompasses a timeframe from January 1986 up until July 2023.

## Data Integrity

The datasets have been generously provided by our 'sponsor,' a distinguished professor in the Economics department of our school. While the data is thorough and well-researched, it's crucial to note that our datasets aren't regularly updated, primarily because they serve the educational motives of this academic project.

## Data Preprocessing

In ensuring the reliability of our predictions, we followed strict guidelines for data preprocessing. The requirements given to us necessitated certain transformations to ensure the data was in the right state for analysis and modeling. Here are the steps we took:

- ### Nominal to Real Oil Price Conversion

    The provided dataset has the oil price in nominal terms, which isn't adjusted for inflation. To extract more meaningful insights that reflect true market dynamics, we converted the nominal oil prices to real prices using the following formula:


```math 
Real Price = Nominal Price/CPI × 100
```

Where:

- **Nominal Price**: The original oil price as provided in the dataset (before inflation adjustment).

- **CPI (Consumer Price Index)**: This reflects the average change over time in the prices paid by consumers. In our dataset, CPI (All items) is represented by the variable `CPIAUCSL` in the macroeconomic data.
This transformation ensured that the price of oil is **adjusted for inflation**, offering a clearer picture of the market dynamics.

## Log Transformation of Macroeconomic Variables

Due to the significant variation in the macroeconomic data on a relative scale, a log transformation was applied to all the variables, with exceptions:

- Variables expressed in percentages, like the Unemployment Rate `UNRATE` and more.

- The log transformation, denoted as
log(x), helps in stabilizing variance and making the data more amenable to modeling.
For this project, we used log(x) *base 2*. The base doesn't matter as long as it's consistent across all variables.

## Dataset Versions

- **Original Dataset**: This is the raw dataset, untouched and as initially provided (no log transformation ONLY real price conversion).
    - Negatives:
    - Zeros:
    - Blanks:
    - Rows:
    - Columns:
    - Variables: 126
    - Dropped Variables: 0
    - Source: [See here]()

- **Transformed Dataset**: After applying the above transformations, this dataset holds the real oil price and the log-transformed macroeconomic variables, ready for analysis and modeling.
    - Negatives:
    - Zeros:
    - Blanks:
    - Rows:
    - Columns:
    - Variables: 126
    - Dropped Variables: 0
    - Source: [See here]()


- **Pruned Dataset**: Here, we've removed any blank entries that might skew our analyses from the transformed dataset.
    - Negatives:
    - Zeros:
    - Blanks:
    - Rows:
    - Columns:
    - Variables:
    - Dropped Variables:
    - Source: [See here]()

- **Refined Dataset**: This version has undergone rigorous cleansing, with negative values, zeros, and blanks meticulously filtered out to ensure data purity, with the original transformations intact.
    - Negatives:
    - Zeros:
    - Blanks:
    - Rows:
    - Columns:
    - Variables:
    - Dropped Variables:
    - Source: [See here]()

## Data Usage

It's essential to understand that while our datasets are extensive and informative, they are primarily tailored for educational purposes within the context of our current project. We advise users to approach the data with a discerning lens, acknowledging its scope and potential limitations.