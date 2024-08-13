

## Retrieval-Augmented Generation (RAG) System

This project implements a Retrieval-Augmented Generation (RAG) system using MistralAI as the generative model and Weaviate as the vector database for semantic search. The system is designed to provide detailed answers to questions by integrating relevant contextual information retrieved from a set of documents.

**Workflow**
1. Document Loading and Splitting

We utilized the langchain library's PyPDF module to load PDF documents. The documents were then split into individual pages for further processing.

2. Chunking

To prepare the documents for embedding, we performed chunking using a recursive character splitter:

    Minimum Chunk Length: 100 characters
    Chunk Overlap: 20 characters

This ensures that the chunks are of manageable size while preserving contextual continuity between chunks.

3. Embedding Generation

We employed sentence-transformers to convert the text chunks into embeddings. These embeddings capture the semantic meaning of the text, enabling efficient and accurate retrieval of relevant information.

4. Semantic Search with Weaviate

The generated embeddings were stored in a Weaviate vector database. Weaviate was used to perform semantic search over the stored embeddings, retrieving documents that are contextually relevant to the input query using cosine similarity.

5. Contextual Answer Generation

The contextual information retrieved from Weaviate was integrated into the MistralAI model, an open-source generative model from Hugging Face. This integration allows the model to provide detailed and contextually accurate answers by leveraging the relevant documents retrieved during the semantic search.
