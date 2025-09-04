## Bagging
Bagging or Bootstrap aggregating enhances the stability and accuracy of machine learning algorithms. This method creates multiple subsets from the original dataset, known as bootstrap samples, by selecting data points with replacement. Each subset trains a separate model. For final predictions, Bagging combines the individual models outputs by using voting or averaging. This approach effectively reduces variance and helps prevent overfitting.

**Note:** Random Forest is a popular algorithm that utilizes bagging by training multiple decision trees on different bootstrap samples and combining their predictions.

![[Pasted image 20250904120528.png]]

### Out of Bag Concept
In bagging, **out-of-bag (OOB)** data refers to instances not included in the bootstrap sample for training a specific base model. Since the process trains each model on random subset of the original data, it naturally leaves out some instances. These OOB instances serves as a built-in validation set for each model, allowing for an assessment of the models performance on unseen data points. You can compute the OOB error, which offers an efficient way to evaluate the models generalization ability. This method eliminates the need for additional validation data or cross-validation process.

![[Pasted image 20250904121002.png]]

- The OOB score is an estimate of performance that mimics cross-validation. It uses out-of-bag samples to estimate the model's accuracy.
- This means that for each tree in a bagging ensemble, only the data not seen by the tree are used to assess that tree's performance.