- When the target variable is continuous value, the prediction task is called as regression.
- Ex. Predicting the temperature from a set input values like wing, humidity, etc.

#### Types of Regression
1. Linear Regression
2. Non-Linear Regression

##### Linear Regression
- Linear regression finds straight line relationship between one dependent variable and another independent variable
- It used to predict continuous target variable by modelling one or more target variables.
- Types of Linear Regression:
	- Simple Linear Regression
	- Multiple Linear Regression

###### Simple Linear Regression
- Simple linear regression models the relationship between the one independent variable and one dependent variable as a straight line
- The equation for Simple Linear Regression is:
 $$ y = \beta_0 + \beta_1x $$
- where:

	- $y$ is the dependent variable
	- $x$ is the independent variable
	- $β_0$ is the intercept
	- $β_1$ is the slope
	![[Pasted image 20250630002548.png]]
###### Multiple Linear equation
- It is same as the simple linear regression but only varies in no. of independent variable as the dependent variable can be dependent on more than one independent variable.
- Equation:
	$$ {y} = \beta_0 + \beta_1x_1 + \beta_2x_2 + \ldots + \beta_nx_ n $$
 - Unlike the simple linear regression gives a straight line, multiple regression gives a plane.


##### Non Linear Regression
###### Polynomial Regression
- It is a subset of the linear regression that includes the polynomial terms i.e. the degree of the independent and dependent variable is greater than 1 unlike the linear regression where degree is 1.
- It is the special case of the multiple linear regression.
- It is used to increase the accuracy. Considering linear regression which works on straight line, it fails to cover all the datapoints and hence the curve is introduced i.e. degree is changed to more than 1.
- Provides the best approximation between the independent and dependent variable.
- ![[Pasted image 20250630003602.png]]

##### Model  Evaluation and Validation Techniques
###### Performance Metrics
- In regression, evaluation metrics gives the quantitative measure of models performance, which helps in assessing and selection of the model.

1. **Mean Squared  Error**
	- It calculates the average of squares of the errors. Errors is the difference between the actual values and the predicted values.
	- A lower value of the MSE suggest a better model performance.
	- $$ MSE =  \frac{\sum_{i=1}^n {(y_{i} - \hat{y_i})}^2}{n}

$$

where,

$$

\hat{y_i} =  \beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}

$$

or We can rewrite :

$$

MSE =   \frac{\sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2}{n}

$$

where

- $n$ is the number of observations

- $p$ is the number of input features

- $x$ is input feature values

- $y$ is actual output

- $\hat{y}$ is predicted output

- $\beta_0$ is Intercept of best fit  line

- $\beta_j$ is Coefficient of Regression for the $j^{th}$ feature

2. **Root Mean Squared Error**
	- As the MSE is hard to interpret in real world data due to square.
	- Hence RMSE is the square root of RMSE, providing measure of the average magnitude of the errors in the predicted values.
	- Since the square root operation reverses the squaring operation MSE, RMSE ends up having same units as the original target variables.
	- Mathematically
		- $$

RMSE =   \sqrt{\frac{\sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2}{n}}

$$

where

- $n$ is the number of observations

- $p$ is the number of input features

- $x$ is input feature values

- $y$ is actual output

- $\beta_0$ is Intercept of best fit line

- $\beta_j$ is Coefficient of Regression for the $j^{th}$ feature

3. **Absolute Mean Error**
	- MAE calculates the average of the absolute errors between actual and predicted values. It is less sensitive to outliers as compared MSE and RMSE.
	- Mathematically:
	- $$

MAE =   \frac{\sum_{i=1}^n |(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))|}{n}

$$

4. **R - Squared**
	- R - squared explains how much variation of the dependent variable 'y' can be attributed to change on independent variable 'x'. R squared value ranges between 0 and 1.
	- **"0" :** This indicates that the model explains none of the variance in the dependent variable. The independent variable has no explanatory powers for the changes in target variable.
	- **"1":** This represents a perfect fit. The model explains all of the variance in the dependent variable. The changes in the 'y' are perfectly captured by the changes in 'x'.
	- While a higher R2 Score generally suggest that a model is a better fit, but it needs to be considered along with other metrics like MSE, RMSE or MAE
	- Mathematically:
$$

\text{R-Squared (r2 score)} =  1 - \frac{\text{RSS}}{\text{TSS}}

$$

where

$$

\text{RSS or SSR or Residual Sum of Squares} =  \sum_{i=1}^n {(y_{i} - (\beta_{0} + \sum_{j=1}^{p} \beta_{j}x_{j}))}^2

$$

$$

\text{TSS or SST or Total Sum of Squares} =  \sum_{i=1}^n {(y_{i} - \overline{y})}^2

$$

where

- $n$ is the number of observations

- $p$ is the number of input features

- $x$ is input feature values

- $y$ is actual output

- $\hat{y}$ is predicted output

- $\overline{y}$ is mean of the target variable