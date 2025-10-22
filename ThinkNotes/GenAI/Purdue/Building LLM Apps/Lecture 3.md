## Langchain Framework (Part 2)

#### Model I/O: Output Parsers
- Output parsers transform the raw output from a language model into a format that is useful and accessible.

#### Document Loaders
- Document loaders are the data injestion for the LLM.
- Langchain supports data loaders for various files: CSV, File Directory, HTML, JSON, and PDF.

#### Text Splitters
- Once the data is loaded from the files or the text is extracted from the docs then the text is divided into the chunks inorder to provide it to LLM.
- Also to maintain the context of the whole file as there is limited context window supported by the LLMs.
	1. **Character Text Splitter:** Splits the text based on the characters, new lines, punctuations or new paragraph.
		- The CharacterTextSplitter divides large text into smaller setions using a defined set of separator characters to determine the chunk size.
		- The Chunk size of the CharacterTextSplitter determines the maximum number of characters in each chunk of text.
		- Usefull for the structured document.
	2. **Recursive Text Splitter:** Splits the text hierarchially i.e maintaining and undertanding the context of the text.
		- Recursive CharacterTextSplitter recursively splits text into chunks for better handling, unlike CharacterTextSplitter, which has a fixed splitting approach.