# XGBoost Model

**XGBoost** stands for **eXtreme Gradient Boosting**. It's an advanced implementation of gradient boosting that is efficient, flexible, and portable. XGBoost is particularly popular due to its speed and performance and is widely used in machine learning competitions for structured or tabular data.

XGBoost improves upon the base gradient boosting by handling null values and regularizing to avoid overfitting. It's known for its scalability that handles various types of predictive modeling problems efficiently.

#### Simple Explanation
At its core, XGBoost builds multiple decision trees sequentially, where each tree tries to correct the mistakes of the previous ones. The *'boosting'* part of the name refers to this idea of building up a strong predictive model by combining many weaker models.

#### Formula

The essence of XGBoost lies in constructing an ensemble of decision trees, with each tree being a series of decisions that lead to a final prediction. When these trees are combined, the final prediction is derived by aggregating the predictions of each individual tree.

The simplified formula for the predicted output `(y-hat)` for each instance `i` in XGBoost is given by the sum of the predictions from `N` trees:

```
y-hat_i = Σ(f_k(x_i)) for k = 1 to N
```

where:

- `y-hat_i` is the predicted value for the `i-th` instance. 
- `f_k` represents the k-th decision tree's prediction function.
- `x_i` is the feature vector for the `i-th` instance.
- `N` is the number of trees in the ensemble.

Each decision tree (`f_k`) is constructed to minimize the overall loss function, which includes a regularization term to control the model's complexity.

Due to the intricate nature of the complete formula, incorporating elements like gradients and regularization, it is quite extensive. For a more detailed mathematical exposition of XGBoost's predictive model, refer to the [XGBoost documentation on the algorithm](https://xgboost.readthedocs.io/en/latest/tutorials/model.html).

#### Parameters
While XGBoost has many parameters, we'll focus on the ones most impactful for our project:

- `n_estimators`: This represents the number of trees you want to build before taking the maximum voting or averages of predictions. Higher numbers of trees can improve the model but can also make your model slower.

- `learning_rate`: Also known as the 'eta' value, it's used to prevent overfitting by making the model more robust by shrinking the weights on each step.

- `max_depth`: This determines how deeply each tree is allowed to grow during any boosting round. Deeper trees can model more complex patterns but can also lead to overfitting.

There are more parameters, but these are the key ones we used. For a deeper understanding, refer to the [XGBoost documentation](https://xgboost.readthedocs.io/en/latest/parameter.html){target=_blank}.

#### Feature Importance
XGBoost provides a way to examine the importance of each feature in the final decision. This is helpful for understanding the model and for feature selection.

`Gain` is the improvement in accuracy brought by a feature to the branches it is on. The higher the gain, the more important the feature is. <br>
Refer to the [XGBoost documentation](https://xgboost.readthedocs.io/en/stable/R-package/discoverYourData.html#feature-importance){target=_blank} for more details on feature importance.

#### Code

To see how we implemented XGBoost in our project including cross-validation, check out the [XGBoost(Regression) notebook](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Models/XGBoost/Cycle-2/Combined-Log-Clean-NoNeg/xgboost-1.ipynb){target=_blank}.