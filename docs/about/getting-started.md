# Getting Started with Oil Price Prediction

Welcome to the *'Getting Started'* section! Here, we'll guide you through accessing and using our predictive models, either via our ***web interface*** or ***directly from the source code in our GitHub repository***.

## Using the Web Interface

Our user-friendly web interface provides a hassle-free experience to run predictions, view results, and model metrics. Here's how you can get started:

1. **Navigate to the Web Interface**: [Here](https://oil-price-prediction.onrender.com/)

2. **Click Predict**: On the homepage you will see a button labeled "Predict".  This will take you to the prediction page, where you can select a model, either Time Series(for forecasting) or Regression(for regression analysis).

3. **Choose a Model**: Browse through the available models via the drop-down selection menu and select the one you'd like to use.

4. **Select Dataset**: Choose from the available datasets via the drop-down menu. We offer three variations to cater to different analysis needs:
    - **Raw Dataset**: The untouched, initial dataset as provided to us.
    - **Pruned Dataset**: Processed to exclude blank or missing entries.
    - **Optimized Dataset**: Extensively cleaned, free of negative values, zeros, and blanks.

For a comprehensive overview of our datasets and the preprocessing methods employed, please visit the [Data section](/docs/data/).

5. **Run the Model**: Once you're ready, click on the 'Predict' button.

6. **View Results**: The results will be displayed in a user-friendly format, showcasing the predictions along with relevant metrics.

7. **Deep Dive**: For users interested in the nitty-gritty details, each model has an accompanying section detailing its background, methodology, and metrics.

## Accessing the Models via GitHub

If you're more hands-on and wish to delve deeper into the code or run the models in your environment, you can access our GitHub repository. Here's how:

1. **Navigate to Our Code Repository**: [Here](https://github.com/Hutto04/The-Oval-Table)

2. **Access the Models Directory**: In the repository, go to the `/Models` folder. Here, you'll find directories for each model, e.g., `Models/Random-Forest`, `Models/XGBoost`, etc.

3. **Explore & Download**: Dive into each model's directory to view the source code, any accompanying documentation, and other relevant files. You can clone the repository or download individual files as needed.

4. **Access the Data**: The data we used for building and training the models is housed under the `/Data` folder. This ensures you have all necessary components to run the models.

5. **Run the Models**: The models were developed in a Python 3.11 environment. Depending on your setup, you might need to install certain libraries or dependencies. Refer to the project's README for specific instructions.

## Need Assistance?
If you encounter any issues or have queries, please check out our [FAQ section](/faq). For more technical problems or feedback, consider raising an issue on our GitHub repository.