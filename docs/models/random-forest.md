# Random Forest Model

**Random Forest** is an ensemble learning method that operates by constructing a multitude of decision trees at training time and outputting the class that is the mode of the classes *(classification)* or mean prediction *(regression)* of the individual trees.

#### Simple Explanation
Random Forest is like a team of decision-makers (trees) where each member (tree) gives a vote (prediction), and the final decision is made based on the majority vote. It's a powerful and versatile machine learning method that can be used for both classification and regression tasks.

The "forest" is made up of many "trees" (hence the name), but unlike real trees, these decision trees are simple models that make predictions based on the features of the data. The "random" part comes from the fact that each tree in the forest is built from a random sample of the data, and at each node in the tree, a random subset of features is considered for splitting. This randomness helps make the model more robust to noise in the data and less likely to overfit, meaning it can generalize better to new, unseen data.

In simpler terms, you can think of Random Forest as a way of asking many different experts for their opinion and then taking the average of all those opinions to make a final decision. Each expert has a different piece of the overall picture, and by combining their knowledge, you get a well-rounded answer.

#### Formula
The prediction of a Random Forest model for a **regression** problem can be expressed as the average of the outputs of all the individual trees in the forest. <br>
For a **classification** problem, it's the majority vote (mode) among the predictions from all trees.

For a regression Random Forest, the predicted value y-hat for a given instance x is calculated as:
```math
y-hat = (1/N) * Σ(tree_k.predict(x)) for k = 1 to N
```

where: 

- `N` is the number of trees in the forest.
- `tree_k.predict(x)` is the prediction for instance `x` from the `k-th` tree.

For a detailed explanation of the Random Forest algorithm and its parameters, you can visit the [Random Forest section in scikit-learn's documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html){target=_blank}.

#### Parameters

- `n_estimators`: The number of trees in the forest.
- `max_depth`: The maximum depth of the trees.
- `min_samples_leaf`: The minimum number of samples required to be at a leaf node.
- `max_features`: The number of features to consider when looking for the best split.

For a detailed explanation of the Random Forest algorithm and its parameters, you can visit the [Random Forest section in scikit-learn's documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html){target=_blank}.


#### Feature Importance
One of the most powerful aspects of Random Forest is its intrinsic ability to rank the importance of features based on how much they improve the purity of the node. This means that more important features will be selected more often when splitting nodes. You can access feature importance in scikit-learn with the `feature_importances_` attribute after fitting a Random Forest model.

Random Forest can capture the importance of features with respect to the task being solved, which is a handy attribute for feature selection and understanding the model.

#### Code

To see how we implemented Random Forest https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Models/ARIMA/Cycle-2/Combined-Log-Transformed/arima-1.ipynbin our project including cross-validation, check out the [Random Forest notebook](https://github.com/Hutto04/The-Oval-Table/blob/main/Maria-Mills/Models/ARIMA/Cycle-2/Combined-Log-Transformed/arima-1.ipynb){target=_blank}.