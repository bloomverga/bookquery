# BookQuery
A project built to chat with PDF documents.

You have a PDF document you want to chat with in other to get insights, this tool is a Jupyter Notebook to consider as a Proof-Of-Concept using the following process:
- Extract text from PDF using ``langchain.document_loaders`` ``UnstructuredPDFLoader``,
- Chunk the result data up into smaller documents using `langchain.text_splitter` `RecursiveCharacterTextSplitter`,
- Create embeddings of the documents using **Open AI Embeddings**,
- Make an indexation of the documents embeddings and store them into a pinecone database,
- Query those documents.

For each user query, we process it as following:
- Create embedding of the user query using **Open AI Embeddings**,
- Make a semantic search in the indexed embeddings database,
- Make a summary of the result using **Langchain question answering** and **OpenAI GPT 3.5 Turbo** model. This summary is the chatbot answer.