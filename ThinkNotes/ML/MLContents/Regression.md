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
-