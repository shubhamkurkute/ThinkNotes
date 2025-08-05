**Hyperparameter:**  While training a model, it uses certain parameters which are set before the actual training of the model.
- Finding the optimal value for the hyperparameters such that model performance is best is hyperparameter tuning.

**There are two approaches for hyperparameter tuning**
1. **Grid Search**
2. **Random Search**

#### Grid Search
- It systematically works through multiple combinations of hyperparameters, it performs exhaustive search on defined parameter grid
- How it Works:
	- Define a parameter grid
	- Combination Evaluation
	- Model Training
	- Optimal Parameters

#### Random Search
- It explores hyperparameters space by sampling fixed number of parameters settings from the specified distributions.
- How it Works:
	- Define a Parameter grid
	- Random Sampling of hyperparameters
	- Model Training
	- Optimal Parameters