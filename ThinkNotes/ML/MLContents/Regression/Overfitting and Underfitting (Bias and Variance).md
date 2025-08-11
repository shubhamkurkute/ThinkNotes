- **When developing ML models, Achieving the right balance between model complexity and simplicity is crucial. This balance is covered by the concepts of overfitting and underfitting.**
### Overfitting
- Overfitting occurs when a model learns the noise and details too well to an extent that it negatively impacts its performance on unseen  data.
- Sign: High Accuracy on training data but poor on test data
- Cause: Model is too complex (Too many parameters or features)

### Underfitting
- Underfitting happens when a model is too simple to capture the underlying pattern of the data.
- Sign: Poor accuracy on training data and test data
- Cause: Model is too simple(Too few parameters or features)

### Bias and Variance Tradeoff
##### Bias
- Errors due to overly simplistic assumptions in the learning algorithm. High bias can cause underfitting
##### Variance
- Error due to excessive complexity in the learning algorithm. High variance can cause overfitting

##### Tradeoff
- **Low Bias and High Variance**: Models fits the training data well but fails to generalize (overfitting)
- **High Bias and Low Variance**: Models does not fit the training data well and misses the underlying trend (underfitting)
- **Optimal tradeoff**: Finding the balance where the model performs well on both training and testing data minimizing overall data. 

