
#### What is Generative AI?
- Generative AI is subset of Artificial Intelligence that focuses on creating models capable of generating new content such as text, image, music and more.
- Gen AI Model learn how data is represented in the form features(not for the purpose of classification or regression )
- Predicting the new features given the target.
- Traditional AI:
	- It is the AI which predicts the target based on the features.
- GenAI:
	- It creates or generates the new features based on the given target. This target is the prompt given to LLMs.

##### Types of GENAI Models
1. GNNs: Generative adversial networks
2. RNN: Recurrent neural networks
3. Variational Models
4. Transformers
5. Autoencoders

### Autoencoders
- Autoencoders a type of neural network compresses the data to generate new images.
- Used in image denoising, dimensionality reduction.
- There are three layers: input layer, hidden layer and output layer.
- Dimension of input and output layer are same and greater than hidden layer.
- Same image should be produced at the output i.e. is given to input.
- But as the hidden layer is in less dimension it forms the information bottleneck.
- Hence it is the responsibility of the hidden layer to learn the important features and produce the same output given as the input.
- The model is trained to generate the same content as the input and hence it is its con. It has flavor of GenAI model as it cannot generate new content

### Recurrent Neural Networks
- RNNs handle sequences and generate text with LSTM networks for context based task.
- Applied in text generation, language translation


### Generative Adversial Networks
- GANs with a generator and discriminator produce realistic images.
- Generator with the noise create some fake image. This image is then classified by the discriminator as a fake or real.
- Once the discriminator classifies it as a fake image, it hurts the generator ultimately pushing generator to reduce the noise and make image little bit realistic.
- This image created is also classified as fake by the discriminator. Then the image is created more realistic by the generator resulting in confusion of discriminator.
- This process is continued until the image looks more realistic keeping discriminator in confusion state. This ultimately results in generation of the realistic image.
- Applications: Used for image-image translation and creating deep fake videos

### Transformers
- Transformers efficiently handle sequences with self attention, popular in NLP.
- Essential for machine translation, chatbots, and text summarization


### Variational Models
- Model represent data distribution, enabling the sampling.
- Applied in image synthesis and semi supervised learning
- Same as Autoencoders it also has three layers: input layer , hidden layer, output layer.
- But as the autoencoders learns fixed points in hidden layer which is not the same case in Variational Models
- This model learns the distribution of the points in its hidden layer.
- This distribution is Gaussian layer
- Therefore it learns the distribution which can be varied by sampling out any point from the distribution hence we call it as a variational.
- This model can generate a new but similar image.
- Limitation: Quality of the image was not great. Sharpness was not up to the mark.