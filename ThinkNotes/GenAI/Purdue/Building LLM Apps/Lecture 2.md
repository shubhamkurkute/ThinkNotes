
## Prompting techniques (Part 2)

3. **Chain of Thought**: This is prompt technique in which we perform sequential prompts after the response in order to get a desired data.
	- In this data may or may be trained by the LLM i.e. we provide the information to the LLM or provide validation to the LLM.
	- It enhances the models reasoning capabilities by outlining intermediate reasoning steps.
4. **Self-Consistency**:  It involves asking LLM same question multiple times and the response which has higher iterations will be considered as the answer.
5. **Tree of Thoughts**:  It allows LLM to consider multiple reasoning paths and self-evaluate choices to decide the next course of action.
	- By maintaining a tree of thoughts model can explore different paths.
	- The model can look ahead and backtrack when necessary to make global choices.
	- It is like breaking the task in small sub-tasks and choosing the best possible solution among it.


## Langchain Framework

#### Prompt Templates
- Prompt templates serve as recipes for language models, offerring a predefined structure ti guide the model's output.

#### Chat Prompt Template
- Chat models interact with users through a series of chat messages.
- Each message has content and is associated with a role, such as an AI assistant, a human or a system.