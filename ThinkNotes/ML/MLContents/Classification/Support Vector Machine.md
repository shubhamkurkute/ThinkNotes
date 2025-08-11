- It is a supervised ML algorithm used for both classification and regression challenges. It is mainly utilised for the classification-related problems.
- In SVM the required straight line to fit the data is called hyperplane.
- The goal of the Support Vector Machine algorithm is to find a hyperplane in an n-dimensional space that distinctly classifies the data points.
- The closest data points to the hyperplane on either side are called Support Vectors
- These support vectors influence the position and orientation of the hyperplane, aiding in the construction of the SVM.
- **There are two types of support vector machines**
	- **Linear SVM:** Separates the data in linear format. If the data set is separated into two using a straight line, the data is linearly separable.
	- **NonLinear SVM:** Is used when data is non-linearly separated. If the dataset cannot be separated into two using a straight line, the data is nonlinear.


#### Hyperparameter Tuning
In Support Vector Machines, hyperparameter plays a crucial role in determining the models performance. here are tkey hyperparameters typically adjusted in SVM
- **Kernel Type:** The kernel function transforms the input data into a higher-dimensional space where a hyperplane can be used to separate classes that are not linearly separable in the original space. Common kernels include:

  * Linear: No transformation is done; suitable for linearly separable data.

  * Polynomial: Transforms data by considering polynomial combinations of the features.

  * Radial Basis Function (RBF): Exploits the distance between the feature vectors in a radial basis. Sigmoid: Uses a sigmoid function to transform data.

- **C (Regularization Parameter):** This parameter trades off correct classification of training examples against maximization of the decision function’s margin. A higher C tries to classify all training examples correctly (low bias but high variance), while a lower C allows more misclassifications but pushes for a larger margin (high bias but low variance).

- **Gamma (γ):** This hyperparameter is used with certain types of kernels like the RBF, where it defines how far the influence of a single training example reaches. Low values mean 'far' and high values mean 'close'. The gamma parameter can be crucial in avoiding overfitting or underfitting in the SVM model.