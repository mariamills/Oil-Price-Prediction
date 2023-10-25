# Introduction

Welcome to the documentation for the **Oil Price Prediction Project**. This project revolves around predicting oil prices using various machine learning models and presenting the results through a user-friendly **web interface** which can be accessed [here]().

## Overview

This project is for the **Software Engineering** course at **Columbus State University**.

Throughout this project, we've been working with a client from the Economics department at our school. Our client has expressed an interest in contrasting the predictive capability of machine learning models against traditional econometric forecasting methods. Through this project, we aim to explore the synergies between technology and economics to achieve more accurate and insightful predictions.

It is a collaborative effort by **The Oval Table**: a team of four students pursuing their Bachelor's in Computer Science. 
The team members are:

[//]: # (   Open in a new tAB LINK)
  - [Maria Mills](https://github.com/mariamills)
  - [Jae Kim](https://github.com/jaekim24)
  - [William Hutto](https://github.com/Hutto04)
  - [Gurpreet Singh](https://github.com/GurpreetCoding)

## Client Requirements

Our project's primary directive stems from the detailed requirements provided by our client, a professor within the economics department. These requirements have shaped the direction and emphasis of our analysis and modeling. Here's a comprehensive breakdown of our client's specifications:

### Data Primary Processing

1. **Real vs Nominal Oil Price**:
   
    **Objective**: Convert nominal oil prices to real oil prices to accurately capture market dynamics by adjusting for inflation.

    **Formula**:

    ```
    Real Price = Nominal Price/CPI × 100
    ```

     - **Nominal Oil Price**: As provided in the dataset (before inflation adjustment).

     - **CPI (Consumer Price Index)**: This reflects the inflation rate and average price changes over time. For our dataset, CPI (All items) can be found as entry #105 in the macroeconomic data.
   
    **Distinction**:

    *Nominal Price*: Not adjusted for inflation.

    *Real Price*: Adjusted for inflation, offering a clearer representation of market dynamics devoid of inflation-induced noise.

2. **Log Transformation**:
   
    **Objective**: Stabilize variance across macroeconomic variables, which exhibit significant relative scale variation.

    **Transformation**:

    ```
    x -> log(x) (base 2)
    ```

    **Exceptions**:

     - Variables expressed as percentages, such as:
         - Unemployment Rate
         - Interest Rates

### Analysis Instructions

**Descriptive Statistics**:

1. Generate descriptive statistics for the transformed real oil price to understand its distribution, central tendency, and variability.

2. Prediction Goal:

     - Predict the near-future real oil price using the Macroeconomic Data at time t.
     - One month ahead (t+1)
     - Potentially extend to 3, 6, or 12 months in the future based on model performance and feasibility.

### Data Splitting Strategy:

- Initially for Cycle 1 we used an 80%/20% train-test split for modeling.

- We plan to also try 50/50 split for Cycle 2, as per client's request.


## Project Goals

- **Data Cleaning:** Clean and preprocess the data to make it suitable for machine learning.

- **Feature Engineering:** Identify relevant features that enhance the predictive power of our models.

- **Modeling:** Implement and evaluate various machine learning models, optimizing for accuracy and precision in predictions.

- **Web Interface:** Develop a user-friendly web application where users can view predictions, understand model metrics, and even run their own predictions with selected models and timeframes.

- **Documentation:** Maintain comprehensive documentation (which you're reading now) detailing every facet of the project, from data processing to user interface guidance.

## Why Oil Price Prediction?

We were only given a choice between three projects, and this one seemed the most interesting. But in all seriousness, oil is a vital commodity that affects the global economy in a myriad of ways. It's also a highly volatile commodity, with prices fluctuating wildly over the years. This makes it an ideal candidate for machine learning, as it's a complex problem that can benefit from the predictive power of modern algorithms.

## Navigating This Documentation

This documentation is structured to provide a comprehensive view of the project:

- **About**: An overview of the project, its goals, and the team behind it.
- **Data:** Dive deep into the data used for this project, including its sources, structure, and processing. 
- **Models:** Learn about each model implemented, their results, and the metrics that showcase their performance.
- **Web Interface:** An overview of the web application, its features, and how to run it.
- **Challenges:** A detailed look at the challenges faced during the project, and the solutions that were implemented to overcome them.
- **FAQ:** A list of frequently asked questions about the project.
- **Conclusion:** A summary of the project, its results, and the lessons learned.

We invite you to explore the documentation and gain insight into the meticulous processes, challenges, and innovative solutions that have shaped this project.
