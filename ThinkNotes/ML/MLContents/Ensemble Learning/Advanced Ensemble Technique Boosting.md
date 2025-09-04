## Boosting

Boosting is a sequential ensemble technique where each model corrects its predecessor's mistakes. The main aim is to train models sequentially, each trying to correct the errors of the previous model. The final prediction is a weighted sum of all the model's predictions. Boosting significantly reduces bias and variance, leading to more accurate model.

**Note:** Popular boosting algorithms include AdaBoost, Gradient Boosting Machines, XGBoost

![[Pasted image 20250904121907.png]]

**Meta Algorithm** involves learning algorithms that are designed to learn how to combine the predictions of multiple machine learning models, often referred to as base models or learners, to improce overall performance.

### AdaBoost Algorithm
AdaBoost, an abbreviation for adaptive boosting, stands as one of the leading boosting algorithms with widespread adoptions. It focuses on classification problems, aiming to transfer, a collection of weak classifiers into single strong classifier. It increase the weights of misclassified instances, directing subsequent classifiers to pay more attention to challenging cases.

**The AdaBoost algorithm follows these steps:**

1. Initially, the algorithm assigns equal weights to all observations in the dataset.
2. A model is constructed using a subset of the data.
3. Predictions are made on the entire dataset using this model.
4. The algorithm computes errors by comparing these predictions to the actual values.
5. In the subsequent model creation, the algorithm assigns higher weights to incorrectly predicted data points.
6. Weights are determined based on error values, where higher errors result in heavier observation weights.
7. This iterative process continues until the error function stabilizes or the algorithm reaches the maximum limit of estimators.

### Gradient Boosting Machine
Gradient boosting refers to a class of ensemble machine learning algorithms tha can be used for classification or regression predictive modelling problems. Gradient boosting is also known as gradient tree boosting, stochastic gradient boosting and gradient boosting machines or GBM for short. Ensembles are constructed from decision tree models. Trees are added one at a time to the ensemble and fit correct the prediction errors made by prior models.
**Gradient Boosting involves three main components:**

* Loss Function: The choice of loss function depends on the type of problem being solved (e.g., regression, classification). The goal is to find a model that minimizes the loss function.
* Weak Learners: Gradient Boosting uses decision trees as the default weak learner. These trees are usually of a fixed size and depth and are created one at a time.
* Additive Model: Instead of adjusting the weights of data points like AdaBoost, Gradient Boosting fits new models to the residual errors made by previous models. Essentially, each new model is built on the errors of the whole ensemble so far.

### XGBoost

XGBoost, or eXtreme Gradient Boosting, stands out as a premier machine learning framework, widely adopted for its proficiency in supervised learning tasks including classification, regression, and ranking. This advanced algorithm builds upon the principles of gradient boosting and is celebrated for its exceptional accuracy and scalability in handling complex predictive modeling challenges.

 **XGBoost offers many essential features that make it ideal for classification tasks. Some of the reasons include:**
* High performance: As mentioned above, XGBoost is optimized for speed and efficiency, making it appropriate for large datasets and real-time applications.
* Regularization methods: L1 (Lasso) and L2 (Ridge) regularisation terms are included in XGBoost to avoid overfitting and increase generalization.
* Handle missing data: Moreover, XGBoost can handle missing data automatically, minimizing the need for preprocessing and imputation.
* Requires Target values to Label Encoded as default nature

### CatBoost
Catboost is a variant of gradient boosting that can handle both categorical and numerical features. It does not require any feature encodings techniques like One-Hot Encoder or Label Encoder to convert categorical features into numerical features.


__Advantages of Boosting__
- It enhances accuracy by reducing both bias and variance significantly.
- It is adaptable and compatible with various types of models.
- It is efficient in complex scenarios where simple models struggle.
 
__Disadvantages of Boosting__
- It is more susceptible to overfitting compared to bagging when dealing with noisy data.
- It demands more computational resources as models are trained sequentially.
- It requires careful parameter tuning to prevent overfitting.