## What is Cross-Validation?

__Cross-Validation__ is a statistical method used to estimate the skill of a machine learning model. It is primarily used to assess how well a model will perform on an independent dataset, i.e., _data it hasn't seen before_. This is crucial for understanding how well your model generalizes from the training data to unseen data.

## Why Use Cross-Validation?

When you build a machine learning model, you typically divide your data into at least __two sets__: a __training set__ and a __test set__.<br> 
The model learns from the training set and is evaluated on the test set. However, this split can lead to variability in the model's performance depending on which data points end up in the training set and which in the test set. __Cross-Validation__ helps to mitigate this by using multiple splits.

## What are 'Folds' in Cross-Validation?

In the context of __Cross-Validation__, the term _"fold"_ refers to each separate iteration, or _"split"_, of the dataset.

- When you perform 5-fold cross-validation, you divide your data into 5 parts (folds).
- In each iteration (fold), a different part of the data is held out as the test set, and the remaining parts are combined to form the training set.
- The model is trained on this training set and evaluated on the test set.
- This process is repeated 5 times (for 5-fold CV), each time with a different part being the test set.

### Why 5 Folds? 
Why did we use 5 folds in our project?<br>

The number of folds is a parameter that you can choose. Five is a common choice because it's a good balance between computational efficiency and reliability of the results. More folds typically mean a better estimate of model performance but require more computation. Fewer folds are quicker but might not estimate performance as accurately.

## What Does Cross-Validation Achieve?

By the end of the cross-validation process, you have an array of performance scores (e.g., accuracy, R^2, MAE, etc.) - one score for each fold. You can then look at the average of these scores to get a more robust understanding of how well your model performs. This average is less sensitive to the particularities of a single train-test split and is generally a better indicator of model performance on unseen data.

## Summary

In summary, __Cross-Validation__ is a method to robustly assess the performance of your machine learning model. By using multiple train-test splits (folds), it gives you a more reliable measure of your model's ability to generalize to new data.

We only performed 5-fold cross-validation in our project, but you can also use other numbers of folds, such as 10-fold cross-validation. 

<br> If you'd like to see our code for cross-validation, go to the model's section of this documentation (located to the left) and click on the link to the model you're interested in. You'll find the code for cross-validation in the `Code' section of the model's documentation, it should take you to that model's notebook on GitHub, scroll down to the bottom of the notebook to find the code for cross-validation.