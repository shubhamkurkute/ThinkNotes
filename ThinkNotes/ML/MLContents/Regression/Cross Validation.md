- Cross validation is the process in which training data is divided in to the multiple folds.
- The combination of this folds is formed such that each fold is used as a test data at least 1 time.
- The results from all the iterations are averaged to provide a robust estimate of model performance.
- There are two strategies:
	- **K Fold Classification**
	- **Stratified K Fold**


#### K-Fold Cross Validation
- In K-Fold cross validation, the dataset is divided into K equally sized folds. The model is trained on K-1 folds and tested on remaining fold.
- This process is repeated k times, with each fold used exactly once as the test test.
- The results are averaged to produce a single performance estimate.


#### Stratified K-Fold Cross Validation
- Similar to K-Fold but ensures that each fold has the same proportion of different classes as the original dataset. This is especially useful for imbalanced datasets.
