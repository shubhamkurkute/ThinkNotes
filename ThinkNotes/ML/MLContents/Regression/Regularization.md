- In linear regression, regularization encompasses a set of techniques used to address the issue of overfitting
- Regularization techniques achieve their objective by introducing a penalty term to the models objective function.
- The objective function which is measured by the MSE is minimized during the training process.

### Regularization term or Alpha
- This is term that scales the penalty term. It controls the strength of Regularization
- Higher alpha: Imposes a strong penalty on the coefficients, leads to greater regularization. This tends to produce a simpler model that may underfit.
- Lower alpha: Imposes a weaker penalty on the coefficients, leads to less restricted regularization, potentially capturing more details in the data but at the risk of overfitting.
- Techniques used for regularization are:
	- Lasso Regression (L1 Regularization)
	- Ridge Regression (L2 Regularization)

### Least Absolute Shrinkage and Selection Operator (LASSO) Regression
- It performs variable selection
- It forces some of the coefficients to be exactly zero with the help of large alpa
- It reduces the learning of more complex model and may address overfitting issue
- It decreases the variance of the model without an increase in bias
- Mathematically,

 - In Regression the objective function is **Residual Sum of Squares** given as

$$

\text{RSS}  =  \sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2

$$

  
  

The Lasso regression penalizes the coefficents by the sum of absolute coefficient controlled by `alpha` and modifies teh objective function as :

$$

 \sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2 + \alpha \sum_{j=1}^{p}|\beta_{j}|

$$

where $\alpha$ can take various values:

- $\alpha = 0$ : Same coefficients as least squares linear regression

- $\alpha = \infty$ : all coefficients are zero

- $0<$ $\alpha<$$\infty$ : Coefficients are between 0 and that of least squares linear regression

### Ridge Regression
- It is useful for handling multicollinear data, where two predictors/independent variables are highly correlated to each other
- Collinearty refers to a situation where two or more predictor variables in a multiple regression model are highly correlated, meaning they have linear relationship.
- This correlation makes it difficult to determine the individual effect of each predictor on the target variable, leading to unreliable and unstable estimates of regression coefficients.
- Ridge regression adds a regularization term to the loss function that penalizes the large coefficients in the model and encourages the model to have smaller coefficients.
- It results in a simpler and more generalized model.
- Ridge Regression does shrink the coefficients, it does not force them to zero, meaning it does not perform feature selection

Mathematically

$$

 \sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2 + \alpha \sum_{j=1}^{p}{\beta_{j}}^2

$$

### Lasso and Ridge Cross Validation
Sklearn offers CV models for both Lasso and Ridge Regression namely LassoCV and RidgeCV. These Models allows us to find out the optimal values for the parameters of base algorithm Lasso or Ridge.