
## What is GraphRAG and how does it works?
In traditional RAG we use vector database to retrieve semantically similar text, but graphRAG incorporates a knowlegde graphs. Knowlege graphs are data structures that store and link related or unrelated data based on the relationships.

### How GraphRAG improves Retrieval
- A Graph RAg retrieval finds the starting point in the network of data via a vector, full text, spatial or other searches and then follow relevant relationships to gather additional information to satisfy the user queries.
- All the captured nodes, relationships and their attributes can be filtered and ranked before being returned as context in the augmentation phase.

### Advantages of GraphRAG
- By navigating the graph structure and following relevant relationships, GraphRAG can retrieve information which may not be directly mentioned in the initial retrieved chunks. This helps in providing comprehensive and contexually relevant response
- GraphRAG's ability to filter and rank the retrieved information, allows it to prioritize the most pertinent information

#### Types of Retrieval
- **Vector (Embedding), Fulltext, Spatial, or other Search Indexes:** Think of this as using keywords or semantic similarity to find initial points of interest within the graph. It's like using a search engine to locate relevant nodes based on your question.
- **Neighborhood Traversal:** This involves exploring the immediate connections of a node. If you've found a person in the graph, this method would show you their friends, family, or colleagues.
- **Path Traversals:** This finds connections between two or more entities. For example, finding the shortest path between two people in a social network, or all the relationships between a disease and a gene.
- **Global Queries:** This uses pre-calculated summaries to answer general questions quickly. It's like having a cheat sheet that provides high-level answers without needing to explore the entire graph.
- **Query Templates:** These are pre-built queries designed for specific types of questions. A domain expert creates these templates to efficiently answer common questions within a particular area.
- **Dynamic Cypher Generation (Text2Cypher):** This uses an AI model to automatically create a database query (Cypher) from your question and the graph's structure. This allows you to ask complex, specific questions without needing to know how to write the query yourself.
- **Agentic Traversal:** An AI agent uses different retrieval methods in a planned sequence to gather information to answer the question.
- **Graph Embedding Retrievers:** This method uses vector embeddings to capture the essence of a node's neighborhood, allowing for fuzzy topological searches by matching candidate embeddings.
- 