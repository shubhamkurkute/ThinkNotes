#### Language Model
- A language model is a model that assigns the probabilities to sequence of words and predicts the next word.
- How does it work:
	- Predicting the next word/ token given previous tokens
	- Learns the syntax, semantics and pragmatics from the raw data.
- Basically predicts the probability of the next word from previous tokens in the vocabulary.

##### History of Language Models
1. **Ngram language model**
	- Based on the words we find probability, such that finding the probability of the next on the previous word.
	- ![[Pasted image 20250706134552.png]]
	- Limitations:
		- Store probability was high
		- No semantics could be found.
		- There could be large number of Ngram could be possible
2. **Neural Network**
	- Word Embedding was Introduced:
		- Vectors or representation of words as numbers such that they capture the semantics.
		- Word Embedding layer: Transform word into a vector.
		- ex: 
			- Input: I am very
			- Concatenated vector = [Embed(I),Embed(am),Embed(very)]
		- Send this embeddings to predict the next word to neural network
	- Limitation:
		- Sequence of word was not maintained.
		- You have to fix the context window. This led to loose the context.
		- Context window is the number of previous words known to predict the next word.
		- Slow and time consuming to train.
3. **Recurrent Neural Network**
	- Addressed the variable length input feature of text processing
	- Also it addressed the remembering of the input sequence.
- ![[Pasted image 20250706140428.png]]
- NN: Neural Network
- t1, t2...tn: Are the timestep.
	- ##### Refer this link for the Neural Network(Encoder-Decoder)
		- ###### Link
			- https://jalammar.github.io/visualizing-neural-machine-translation-mechanics-of-seq2seq-models-with-attention/
4. **Transformers Architecture**
	- This architecture takes in input sequence and reads it in parallel, processes the hidden states of the decoder. The decoder then produces output tokens one by one.
	- This good model to solve Machine Translation, Text Summarization, Question Answering where you have a stream of input tokens to understand(encoder) and then generate a stream of output tokens(decoder)
	- Encoder: Understands the input
	- Decoder: Generates the output based on encoders input to the decoder.
	- ##### Refer this link for transformer
		- ###### Link:
			- [https://jalammar.github.io/illustrated-transformer/](https://jalammar.github.io/illustrated-transformer/ "https://jalammar.github.io/illustrated-transformer/")

- **BERT**: Encoder only model. Used to solve the classification problem that does not require stream of outputs
- **GPT**: Decoder only model which does not require input and generates the stream of output. This generates and selects the next word based on highest probability.