- Classification is supervised machine learning technique where the model is trained to predict the class label of given input data.
- It tries to predict a categorical variable and not the continous variable
- It looks for a decision boundary, which divides the dataset into different classes.

#### Binary Classification
- binary classification is the simplest type of classification, where the model tries to predict one of the two possible outcomes .
- For example Yes or No, True or False
- **Popular Algorithms**
	- Logistic Regression
	- Naive Bayes
	- K Nearest Neighbors
	- Decision Trees
	- Support Vector Machines

### Logistic Regression
- Logistic regression is a supervised learning algorithm primarily used for binary classification.
- In this method, we apply sigmoid function to the linear combination of independent variables/predictors.
- This produces a probability value between  0 and 1.
- This probability represents the likelihood of a datapoint belonging to particular category or class
- If the estimated probability is greater than equal to $\geq$ 0.5, then the model predicts that the instance belongs to a positive class labeled “1” or else it predicts that it does not (i.e., it belongs to the negative class, labeled “0”). This makes it a binary classifier.

##### Mathematical Representation of Logistic Regression
1. **Logistic Function (Sigmoid Function)**: The core of the logistic regression is the logistc function, also known as Sigmoid Function, which maps any real valued number in range of (0,1).
$$

\sigma(z) = \frac{1}{1 + e^{-z}}

$$
- Where,
	- `z` is a linear combination of the input features. This function outputs the probability of the input belonging to the positive class (class 1).
2. **Linear Combination of Input**: 
	- The input features 𝑋 are combined linearly using weights 𝑤 and a bias term 𝑏:
$$

z = w \cdot X + b

$$
3. **Prediction**:
	- The logistic regression model predicts the probability of the class being positive or negative (class 1 or class 0) as:

$$

\sigma(z) = P(y=1 \mid X) = \frac{1}{1 + e^{-(w \cdot X + b)}}

$$

  

	 - To make a final binary decision, a threshold (usually 0.5) is applied to this probability. If 𝜎(𝑧)≥0.5, the prediction is class 1; otherwise, it's class 0.

4. **Cost Function**:
	  - The cost function used in the logistic regression is the binary cross entropy, which measures the discrepancy between the predicted probabilities and the actual class labels.
$$

J(w, b) = -\frac{1}{m} \sum_{i=1}^m \left[ y_{(i)} \log(\hat{y}_{(i)}) + (1 - y_{(i)}) \log(1 - \hat{y}_{(i)}) \right]

$$
    - Where 𝑚 is the number of training examples, $y_{(i)}$ is the true label, and $\hat{y}_{(i)}$ is the predicted probability for the $𝑖^{th}$ example.

#### Performance Metrics Used in Classification
- A performance Evaluation matrix, referred as confusion matrix in the context of classification problems is the tool to assess the performance of the predictive model by comparing the actual outcomes with the predicted outcomes.
- In Binary class classification a confusion matrix is essentially a 2x2 matrix
- The matrix includes the following components:
	- **True Positive (TP)**: The number of instances where the model correctly predicted the positive class
	- **True Negative (TN)**: The number of instances where the model correctly predicted the negative class.
	- **False Negative (FN)**: The number of instances where the model incorrectly predicted the negative class.(Type 2 error)
	- **False Positive (FP)**: The number of instances where the model incorrectly predicted the positive class.(Type 1 error)

1. **Accuracy Score**: The Ratio of correctly predicted instances(both positive and negative) to the total instances
$$ \text{Accuracy} = \frac{\text{TP} + \text{TN}}{\text{TP} + \text{FP} + \text{TN} +\text{FN}}$$
2. **Precision**: The ratio of correctly predicted positive instances to the total positive predictions.
	- It indicates the quality of the positive predictions
	- It is a good metric to consider when the cost of false positive is high.
$$ \text{Precision} = \frac{\text{TP}}{\text{TP} + \text{FP}}$$
3. **Recall or Sensitivity or True Positive Rate**: The ratio of correctly predicted positive instances to the actual positive instances
	- It measure the models ability to detect the positive class.
	- It is a good metric good to consider when the cost of false negative is high.

4. **F1 Score**: The Harmonic mean of precision and recal. Its a single metric that balances tradeoff between precision and recall
$$

\text{F1 Score} =  2 \times \frac{\text{Precision}\times \text{Recall}}{\text{Precision} + \text{Recall}}

$$

5. **ROC curve: Receiver Operating Characteristics Curve**: An ROC curve is a graphical representation of a classification model's performance across different classification threshold.
	- It plots the True Positive Rate (Recall) againt the False Positive Rate (FPR) at various threshold settings.
	- True Positive Rate (TPR) or Recall
		$$ \text{TPR} = \frac{TP}{TP + FN} $$
	- False Positive Rate (FPR) :
		$$\text{FPR} = \frac{\text{FP}}{\text{FP} + \text{TN}}$$
	- **Finding the Optimal Threshold**:  The default threshold for many classification algorithms is 0.5, meaning if the predicted probability is greater than 0.5, the instance is classified as positive. However, this threshold may not always be optimal, especially in cases with skewed class distributions or when the costs of false positives and false negatives are unequal.
	- **Methods to Find Optimal Threshold**:
		1. *Maximizing Youden’s J Statistic* : 
			- Youden's J statistic is defined as: $J=TPR−FPR$
			- The optimal threshold is where this statistic is maximized. This method balances the TPR and FPR, aiming to mazimize the true positives while minimizing the false positives
		2. *Closest Point to (0,1)*: Another method is to find the point on the ROC curve that is closest to the top-left corner (0,1), representing the ideal classifier with TPR = 1 and FPR = 0

6. **AUC - Area Under Curve** : The AUC is a single scalar value that summarizes the overall performance of a classifier.
	- *AUC Value*:
		- An AUC value of 0.5 suggest no discrimination, meaning the model performs no better than random chance
		- An AUC value of 1 indicates the perfect discrimination, meaning the model perfectly distinguishes between positive and negative class.