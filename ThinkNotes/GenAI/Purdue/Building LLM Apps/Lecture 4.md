## Introduction to Vector Store
- If the model needs to recall, compare and reason over knowledge efficiently, the vectore store is where all the magic happens.
- The vectorstore acts as a storage space for embeddings. It helps quickly find and work with data representatons, improving the models performance.

#### 1. VectoreStore: FAISS
- FAISS is a high performance library built for efficient similarity search at scale.
	- Ease of Integration
	- Scalability
	- Speed
- Ideal for production environments requiring large-scale data handling and low-latency retrieval.

#### 2. VectorStore: PineCone
- PineCone is a fuly managed, cloud-native vector database that ensures high availability and global indexing.
	- Ease of Integration
	- Scalability
	- Global reach
- Best suited for applications that demand high performance, scalability and minimal operational overhead in a cloud environment.

#### 3. VectorStore: ChromaDB
- ChromaDB is a lightweight, user friendly vector store designed for local storage of embeddings. 
	- Ease of use
	- Local Deployment
	- Cost-effective
- Perfect for moderate data volumes and quick similarity searches in development environments.

## Langchain Retriever
- The retriever is an abstraction layer built on top of it , it defines how to fetch , filter and rank the relevant pieces.
-  Retrievers take a string query input and return a list of document objects as output

## Langchain Chains
- Chains helps us connect multiple components  like LLMs, prompts, retrievers, and tools into one seamless pipeline
- In applications of LLMs, chaining typically involves integrating a prompt template with the LLM and, if necessary, employing an output parser for further refinement.
 - Types of chains:
	 - **Sequential Chain:** A sequential chain in langchain allow you to execute multiple chains in sequence, much like a well-orchestrated syphny.
		 - It allows to create a sequential chain.
	- **Stuff Chain:** The stuff chain in LLM generates creative content based on specific prompts, assisting in brainstorming and idea generation with language models.
		- The stuff chain stuffs multiple docments into the single and prompt and then passes to model.
		- This chain particularly useful when the documents are multiple small documents.
	- **Map Reduce Chain:** The map reduce chain in LLMs simplifies complex task by dividing them into smaller pieces, processing each independently and then combining the results.
		- Map Phase: Break it down
		- Reduce Phase: Combine it all

## Langchain Memory
There are several type of memery:
1. **ConversationBufferMemory:** It keeps the full chat history from the start - nothing is forgotten.
2. **Conversation Buffer Window Memory:** This memory has a context window to store the no. of past conversation it should save or remember.
	- Stores the last N interactions user + AI interactions in a rolling window.
3. **Conversation entity memory:** Extracts and tracks named entities (like people, places or products) mentioned during the chat
4. **Conversation summary memory:** This memory summarizes the past interaction or the messages recursively with the help of another LLM. Can be used to reduce the token size by replacing the long histories with a concise summary.