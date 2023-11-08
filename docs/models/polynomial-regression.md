# Polynomial Regression Model

**Polynomial Regression** extends the linear model by adding extra predictors, obtained by raising each of the original predictors to a power. This method provides a way to model a non-linear relationship between the dependent and independent variables.

#### Simple Explanation

Polynomial Regression is like giving a line in our graph the freedom to curve and bend. It’s especially useful when the relationship between variables isn't straight-forward or linear.

#### Formula

The model's formula is:
```math
y = β₀ + β₁x₁ + β₂x₁² + ... + βₙx₁ⁿ + ε
```

Here, `y` represents the dependent variable we're trying to predict, `x₁` is the independent variable, `β₀` is the y-intercept, `β₁` to `βₙ` are the coefficients for each degree of the independent variable, and `ε` is the error term.

#### Parameters

Some key parameters in Polynomial Regression include:

- The degree of the polynomial (`n`), which determines the curvature of the fit.
- The coefficients (`β₁` to `βₙ`), which are adjusted during the training process to fit the curve to the data.

Unlike some other models, Polynomial Regression does not have an intrinsic feature importance metric. However, the size of the coefficients can give some indication of the importance of each term.

#### Feature Importance

Polynomial Regression doesn't directly provide feature importance. However, the magnitude of the coefficients can imply how much influence each degree of the independent variable has on the dependent variable.

For a detailed understanding of Polynomial Regression, you can refer to the [documentation](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html){target=_blank}.

