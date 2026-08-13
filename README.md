# agentic-ai-rag-langchain
# Agentic AI RAG with LangChain & Gemini

A hands-on project demonstrating **Retrieval-Augmented Generation (RAG)** and **Agentic RAG** using **LangChain**, **Google Gemini**, **FAISS**, and Python.

## 📌 About the Project

This project explores how Large Language Models can use external knowledge through Retrieval-Augmented Generation.

The notebook builds a RAG system using an Internet history knowledge base and then extends it into an **Agentic RAG** system where an AI agent can decide when to use a retrieval tool to find relevant information.

## 🚀 Technologies Used

* Python
* Google Gemini
* LangChain
* Agentic RAG
* Retrieval-Augmented Generation (RAG)
* FAISS
* Google Generative AI Embeddings
* Sentence Transformers
* Google Colab

## 📚 Topics Covered

### 1. Gemini API Configuration

* Configure the Gemini API key
* Securely access `GEMINI_API_KEY` using Google Colab Secrets
* Initialize a Gemini model through LangChain

### 2. Document Processing

The project creates an Internet history knowledge base and processes it for retrieval.

The document is:

* Converted into LangChain `Document` objects
* Split into smaller chunks
* Processed using `RecursiveCharacterTextSplitter`

The chunking configuration uses:

* Chunk size: 500 characters
* Chunk overlap: 50 characters

### 3. Embeddings

Google Generative AI Embeddings are used to convert text chunks into numerical vector representations.

The project uses:

```text
models/gemini-embedding-001
```

### 4. FAISS Vector Store

The generated embeddings are stored in a **FAISS vector store**.

FAISS is used to efficiently perform similarity searches and retrieve the most relevant document chunks for a given question.

### 5. Traditional RAG

The project implements a basic RAG pipeline consisting of:

```text
User Query
     ↓
Retriever
     ↓
Relevant Documents
     ↓
Prompt
     ↓
Gemini LLM
     ↓
Final Answer
```

The retriever is configured to return the top 2 relevant chunks.

The RAG prompt instructs the model to use only the retrieved context when answering questions.

### 6. Agentic RAG

The project then extends the basic RAG system into an **Agentic RAG** workflow.

A custom retrieval tool is created using LangChain's `@tool` decorator:

```python
retrieve_internet_context
```

The agent can use this tool to retrieve relevant information from the Internet history knowledge base.

The workflow is:

```text
User Query
     ↓
AI Agent
     ↓
Decide Whether Retrieval Is Needed
     ↓
Retrieval Tool
     ↓
FAISS Similarity Search
     ↓
Retrieved Context
     ↓
Gemini LLM
     ↓
Answer
```

## 🧠 Key Concepts

* Retrieval-Augmented Generation
* Agentic RAG
* Large Language Models
* Vector Embeddings
* Vector Databases
* Similarity Search
* Document Chunking
* LangChain Retrievers
* LangChain Tools
* AI Agents
* Google Gemini

## 🔧 Libraries Used

```bash
pip install -U langchain-google-genai langchain-community langchain
pip install -U sentence-transformers faiss-cpu langchain-chroma langchain_text_splitters
```

## 🔑 API Key Setup

This project requires a Google Gemini API key.

In Google Colab:

1. Open the **Secrets** panel.
2. Add your Gemini API key.
3. Name the secret:

```text
GEMINI_API_KEY
```

**Never upload your API key or other secret credentials to GitHub.**

## ▶️ How to Run

1. Open the notebook in Google Colab.
2. Add your `GEMINI_API_KEY` to Colab Secrets.
3. Install the required libraries.
4. Run the notebook cells in order.
5. Experiment with different questions related to the Internet history knowledge base.

## 📂 Project Structure

```text
agentic-ai-rag-langchain/
│
├── Agentic_ai_RAG.ipynb
└── README.md
```

## 🎯 Learning Outcomes

Through this project, I gained practical experience in:

* Building a Retrieval-Augmented Generation system
* Creating document chunks for retrieval
* Generating vector embeddings
* Using FAISS for similarity search
* Connecting Gemini with LangChain
* Building retrieval chains
* Creating custom LangChain tools
* Building an Agentic RAG workflow
* Understanding how AI agents interact with retrieval tools

## 👩‍💻 Author

**Sandhya Peram**

GitHub: [@peramsandhya41](https://github.com/peramsandhya41)

---

⭐ If you find this project useful, feel free to star the repository!
