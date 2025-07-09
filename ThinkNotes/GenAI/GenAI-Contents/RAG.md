## Retrieval Augmented Generation.

#### Retrieval 
- From a repository of documents stored as chunks get the most similar chunk(s) based on vector similarity of user's query.
- Retrieval is done on the matching of the vector presentation of query to the vector representation of documents.

#### Augmentation
- Join the contents of all the retrieved chunks previously into large text(content).

#### Generation
- Use the context to answer the user's query in the desired format using LLM