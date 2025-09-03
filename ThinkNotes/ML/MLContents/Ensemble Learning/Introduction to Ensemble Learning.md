Ensemble learning combines multiple models to enhance the overall performance of ML algorithms. The fundamental principle of ensemble learning is combining predictions from multiple individual models to produce a more accurate and robust prediction than a single model.

**Goals of Ensemble learning**
- Enhance predictive accuracy by combining multiple models
- Improve model robustness and generalization performance


#### Weak and Strong Learners
- **Weak Learner or Base Learner** : Is a learning algorithm capable of producing with probability of error strictly less than that of random guessing
- **Strong Learner**: Is able to yield classifiers with arbitrarily small error probability. It performs much better than random guessing

An ensemble of classifiers is a classifier build upon some combination of Weak Learner. The strategy of boosting and ensembles of classifiers, is to learn many weak classifiers and combine them instead of trying to learn a single strong learner

#### Categories of Ensemble Learning
1. Sequential Ensembling Techniques
2. Parallel Ensembling Techniques

### Sequential Ensembling Tecniques
These techniques train models sequentially, with each model attempting to correct its predecessor's errors. This technique focuses on improving the overall performance of the ensemble by iteratively refining predictions. An approach is boosting.

**Note**: It typically emplys weak learners as base estimators because these learners initially have error rates.

The steps involved in the sequential ensemble technique depend on the data structure and the requirements of the application. They are:
1. __Base Model Selection__: Choose the initial model.
2. __Sequential Training__: Train models one after the other.
3. __Error Correction__: Each model learns from previous mistakes.
4. __Prediction Refinement__: Iteratively refine predictions.
5. __Combining Predictions__: Combine predictions from all models.
6. __Evaluation__: Assess ensemble performance using metrics

![[Pasted image 20250904000916.png]]

__Note:__ If all four base models are of the same type, it is considered to be a homogeneous ensemble. If they are different, it is considered heterogeneous.

The diagram above shows the training data divided into four samples, with each sample trained on a distinct base model. Insights gained from model M1 are passed to model M2 alongside sample S2. M2 then adjusts its weights and biases based on the outcomes of M1. This process repeats for models 2, 3, and 4. Finally, all the learners are combined using a weighted averaging strategy.
The summation sign ($ ∑ $) indicates the function that adjusts the model to improve its overall performance

__The sequential ensemble technique is employed when dealing with:__
- Complex relationships between input features and the target variable
- Diverse data types, including numerical, categorical, and textual data
- Imbalanced datasets, where skewed class distributions pose classification challenges.
- Incremental updates are needed to adapt models gradually to evolving data over time


### Parallel Ensembling Technique
The parallel ensemble technique concurrently trains models. They combine the predictions from multiple models to improve the final output. Bagging and Random Forest algorithms are examples of parallel ensemble techniques.
__Note:__  It employs stronger learners as base estimators.
The steps involved in the parallel ensemble technique are:
1. __Data Partitioning__: Divide the dataset into subsets
2. __Model Training__: Train models concurrently on subsets
3. __Prediction__: Models make independent predictions
4. __Combining Predictions__: Aggregate predictions using techniques like voting or averaging
5. __Evaluation__: Assess ensemble performance using metrics


![link text](https://labcontent.simplicdn.net/data-content/content-assets/Data_and_AI/ML/Lesson_07/Parallel_Ensemble_Technique.png)

  
In the above diagram, the training data is divided into four samples, labeled S1 to S4, each trained on a distinct base model (M1 to M4). Unlike the sequential ensemble technique, the data in the base learners is independent. This independence of base learners significantly reduces the error due to the application of averages.
The summation sign ($ ∑ $) indicates the aggregated model with improved performance, which has been learned from all independent base models, M1 to M4.
The parallel ensemble technique is used to:
- Enhance scalability, allowing for the efficient processing of large volumes of data by distributing the workload
- Expedite training and prediction processes through parallel computation on multi-core systems.
- Reduce susceptibility to noise and overfitting by averaging out individual model errors.
- Capture diverse data patterns effectively by utilizing different models trained on varied data subsets

## Simple Techniques used in Ensemble Learning
There are 2 major strategies used as simple technique in ensemble learning
- **Voting:** Used for classification
- **Averaging:** Used for regression

#### Majority Voting/ Hard Voting
Majority Voting or Hard Voting is an ensembe learning classification technique. It involves multiple models, making predictions for each data point. Each models prediction is considered a vote. The final prediction is determined by the majority vote among the models.
**Example**:
- Majority Voting ensemble works on a breast cancer classification by combining predictions from multiple individual classifiers, such as Logistic regression, Decision Tree, and SVM
- Each classifier provides its prediction for whether a given sample belongs to a certain class. The voting ensemble then aggregates these predictions using a voting mechanism
- The final prediction is determined based on the most commonly predicted class among the classifiers
- This approach leverages the collective wisdom of the diverse models to improve overall prediction accuracy and robustness in breast cancer classification tasks.

#### Weighted Voting/ Soft Voting
Soft voting takes into account the probability estimates for each class provided by the models, assuming the models are capable of estimating these probabilities. The final prediction is determined by averaging these probabilities across all models, and the class with the highest average probability is selected.