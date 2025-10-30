## Fine Tuning Part 2

### Fine Tuning Methodologies
1. **Supervised Fine Tuning (SFT):** 
	- It customizes the model for a task with labelled data, the target model borrows designs from the source model, tweaking parameters except the output layer. This boosts transfer learning and accuracy.
	- Supervised fine-tuning is like giving a model extra training with specific examples and clear labels. It helps the model get a etter at understanding and predicting.
	- Supervised fine-tuning on Q/A pairs
	- **Parameter-Efficient Fine-Tuning (PEFT)**
		- PEFT is technique used in NLP to improve the performance of pretrained language models on specific tasks while significantly reducing computational requirments.
		- PEFT enables fine-tuning a small subset of parameters in a pretrained LLM. making it more efficient and cost-effective.
	- **PEFT Techniques:**
		- **LoRA (Low rank adaptations):**
			- It introduces trainable parameters into the transformer layers to enable the model to learn specific representations.
			- It adds low-rank trainble layers instead of modifying the entire model while keeping most of the model weights frozen.
		- **P-tuning (Prompt Tuning):** 
			- It adds a learnable prompt to the input to help the model adapt to new tasks.
			- P-tuning trains special word-like embeddings instead of changing the model itself
		- **Prefix Tuning:** It enhances the task-specific learning in transformers by adding trainable tensors to each block.
		- **Adaptors:** They add tunable layers to LLMs transformers blocks for task learning
		- **AdaLoRA:** It extends LoRA, enabling fine-tuning on quantized weights for efficient training
	
2. **Reinforcement Learning with Human Feedback (RLHF):** 
	 - The RLHF method aims for gradual improvements, trying strategies like regularization or changing the model structure. Engineers can refine the model iteratively until it reaches the desired performance level.
	 - RLHF is about training the LLMs using the human feedback, helping them follow instructons and providing quality judgments.
	 - This phrase refers to a type of machine learning where a model is trained and adjusted based on feedback provided by the humans.
	 - The RL policy a copy of the original model, adjusts its behaviour based on feedback to generate responses preferred according to rewards.
	 ![[Pasted image 20251030152307.png]]

#### HyperParameter Tuning in Fine-Tuning
- Hyperparameter adjusting is essential when fine-tuning language models for optimal performance.
- These parameters are set before the model learns, helping to shape its performance.