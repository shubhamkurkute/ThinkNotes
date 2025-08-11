- The K-Nearest Neighbor algorithm is a popular machine learning technique used for classification and regression tasks.
- It relies on the idea that similar data points tend to have similar values or labels
- During the training phase, the KNN algorithm retains the entire training dataset as a reference.
- For predictions, it computes the distance between the input data point and all training examples using a selected distance metric, such as Euclidean distance
- **Steps:**
	1. Load the training and test data
	2. Choose the value of K, which represents the number of the neighbors to consider. (K can be any positive number)
	3. For every point in the test data, do the following:
		- Calculate the distance between the test data point and each point in the training dataset using a distance metric such as Euclidean, Manhattan,Minkowski or Hamming distance.
		- Sort the calculated distances in ascending order.
		- Select the top K closest data points (smallest distances) from the sorted list.
		- Assign the most frequent class (mode) among these K nearest neighbors to the test data point in classification problems.
		- Take the Average of these K nearest neighbors to the test data point in Regression problems.

#### Hyperparameter Tuning of KNN
- The number of Neighbors k is crucial hyperparameter in K Nearest Neighbors algorithm.
- It specifies how many nearest neighbors should be considered for making predictions.
- The selection of K impact the models capability to generalize effectively: a small *k* can make the model sensitive to the noise, potentially lead to overfiiting.
- While the larger *k* might include less relevant neighbors, possibly cause underfitting.