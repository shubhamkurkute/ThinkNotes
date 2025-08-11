- A Decision Tree is non parametric `(takes zero or very few assumptions)`  Supervised Machine Learning Algorithm used for both classification and Regression.
- It has a hierarchial tree structure which consist of root node, branches, internal/decision Nodes, leaf nodes.
- **How Decision Trees Work**
	1. Creating a decision trees involves a series of steps aimed at systematically breaking down the  dataset based on its features to achieve nest possible classification.
		- **Selecting Best Atrribute:** Choosing the best atrribute to split data using metric like *Gini Impurity, Entropy and Information Gain*
		- **Splitting the Dataset:** The dataset is divided into sunsets on the values of the selected attribute.
		- **Repeating the Process:** The process is repeated recursively for each subsets, creating new internal nodes or leaf nodes until a stopping criterion is met.

#### Metrics for Splitting
1. **Gini Impurity:** Gini Impurity is the measure of the impurity or disorder in set of elements. This metric measures the liklihood of incorrectly classifying a randomly chosen element. The value for gini impurity ranges from 0 (perfectly pure) to 0.5 (maximum impurity in a binary classification problem).
	- Mathematically:
		 $$ Gini =  1- \sum_{i=1}^{n}{(p_{i})}^2$$
		- where $p_{i}$ is the probability of an instance being classified into class *i*
2. **Entropy:** Entropy quantifies the amountof uncertainity in the dataset 
	- Mathematically:
		$$ Entropy =  - \sum_{i=1}^{n}{p_{i}.log_{2}(p_{i})}$$
	- where $p_{i}$ is the probability of an instance being classified into class *i*
3. **Information Gain:** This metric measures the reduction in entropy or Gini impurity after the dataset is split on an attribute.
	- Mathematically:
		$$ \text{Information Gain} = \text{Entropy(Parent)} - \sum_{i=1}^{n}( \frac{|D_{i}|}{|D|} \times \text{Entropy}D_{i} )$$
	-  where $D_{i}$ is the subset of D after being split by an attibute.

#### Advantages
- Simplicity and Interpretable
- Versatile
- No Need of Scaling
- Handle Non Linear Relationship

#### Disadvantages
- Overfitting
- Instable
- Biased

### Pruning
To address the issue of overfitting, decision tree can be pruned. Pruning involves removing the parts of the tree that do not provide significant power to classify. There are 2 way to achieve this:
- **Pre- Pruning(Early Stopping)** - Halts the growth of tree early based on a stopping criterion such as max depth or minimum number of samples required to perform split.
- **Post Pruning** -  First grows the full tree and then removes nodes that add little predictive powerto reduce the complexity of the model.