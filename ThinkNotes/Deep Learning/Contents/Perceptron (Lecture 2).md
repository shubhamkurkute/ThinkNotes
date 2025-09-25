Perceptron is simple neural network design for binary classification problem and only consist of single neuron. Takes linear summation of inputs and there is a step function.
**Step Function:** If the value of summation of inputs is greater than 0 then it is divided into class 1 by step function.

### FeedForward Neural Network
This is a type of neural network where the data flows into the one direction i.e. forward. The information flows only from the input layer to the output layer through the hidden layer.
- It cannot remember the things happen in the past, except its training
- The information never touches the node twice.
- It has no memory of inputs it receives


### Multilayer Perceptrons
They are type of FFN that creates a collection of outputs from a set of inputs.


### Activation function
- Is to modified the linear summation to understand the data better . Also activation function confines the inputs into a certain range like 0 to 1 or -1 to +1 based on the type of activation function used.
- The sum of products of inputs and weights is passed to an activation function.
- The activation function is needed in NN to introduce the non-linearity and enable the model to learn complex relationships and make more expressive predictions.
![[Pasted image 20250926001717.png]]

#### Types of activation functions:
1. **Step Function**
2. **Sigmoid Function**
3. **ReLU (Rectified Linear Unit)**
4. **Softmax function**

### Step Function
A perceptron gets activated whenever the sum of weights and  inputs is non-zero and positive.

### Sigmoid Function
The sigmoid activation function produces an output in the range of 0 to 1. making it useful for binary classification tasks.

### ReLU
If he value of input to a neuron is zero or less, ReLU assigns 0 as the output value. If not the output is equal to the input.

### Softmx
- The softmax function is variant of the sigmoid function, is particulary usefull for handling multiclass classification problem.
- It is commonly found in the output layer of the image classification problems
- It normalizes outputs for each class to fall between 0 and 1.
- It achieves this by dividing each output by the sum of all outputs.
