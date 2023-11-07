## Client Data Processing Requirements

#### Objective
The goal is to use macroeconomic indicators to predict the real oil price in the near future, starting with a one-month forecast and potentially extending to 3, 6, and 12 months.

#### Data Transformation Steps
1. Convert Nominal to Real Oil Prices
    - **Nominal Oil Price**: The original oil price data provided.
    - **CPI (Consumer Price Index)**: A measure of inflation, found as variable #105 in the macroeconomic data.
    - **Real Oil Price Calculation**: Adjust the nominal oil price for inflation using the formula: `Real Price = Nominal Price / CPI * 100`.
    - **Purpose**: Real prices provide a clearer picture of market dynamics by removing the distortion caused by inflation.
2. Log Transformation of Macroeconomic Variables
    - **Log Transformation**: Apply a logarithmic scale to the macroeconomic variables to stabilize variance and reduce skewness.
    - **Exclusions**: Do not transform variables that are already in percentage form (e.g., interest rates, unemployment rate) (and of course the 'date' column).
    
    #### **Why Log Transform?**:
    - It helps in dealing with large variations in data, making patterns more perceptible and the data more suitable for modeling.
    - **Handling Zero Values**: Since the logarithm of zero is undefined, we add a tiny constant (1e-6) to all values before transformation. This is a common practice to avoid mathematical errors without significantly altering the data.

3. Data Splitting for Model Training and Testing
   **Initial Split**: Use 80% of the data for training the model and 20% for testing.
   **Alternative Split**: Consider a 50/50 split for comparison.
4. Descriptive Statistics
   **Post-Transformation Analysis**: Provide descriptive statistics for the real oil prices to understand their distribution, central tendency, and spread.

### Notes on Data Transformation
   - **Log Base**: The base of the logarithm used in transformations is typically base 10 or base e (natural logarithm) in pandas when using np.log.
   - **Small Constant Addition**: The addition of `1e-6` is to ensure no log transformation involves a zero value. Given the smallest non-zero values in the dataset are significantly larger than `1e-6`, this addition will not materially affect the data.
   - **Data Integrity**: Ensure that all transformations preserve the integrity of the data, maintaining its original meaning and relationships.