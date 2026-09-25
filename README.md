# 🧠 RAG Document QA

A Retrieval-Augmented Generation (RAG) application that allows users to search and ask questions across multiple document formats using semantic retrieval and an LLM.

## 🎯 Overview

This project combines document processing, text chunking, embeddings, vector search and LLM generation to build a practical document question-answering system.

### Supported Documents

* PDF
* TXT
* CSV
* XLSX
* DOCX
* JSON

## ✨ Features

* 📄 Multi-format document ingestion
* ✂️ Semantic text chunking
* 🔢 Sentence Transformer embeddings
* 🔎 FAISS vector similarity search
* 🧠 Context-aware retrieval
* 🤖 LLM-based answer generation
* 💾 Persistent vector index
* 🔐 Environment-based API key configuration

## 🏗️ Architecture

```text
Documents
    ↓
Document Loader
    ↓
Text Extraction
    ↓
Chunking
    ↓
Sentence Transformer
    ↓
Embeddings
    ↓
FAISS Vector Store
    ↓
User Query
    ↓
Similarity Search
    ↓
Retrieved Context
    ↓
LLM
    ↓
Generated Answer
```

## 🛠️ Tech Stack

* Python
* Sentence Transformers
* FAISS
* Groq
* LangChain
* NumPy
* Pandas

## 📁 Project Structure

```text
Rag-Document-qa/
│
├── app.py
├── main.py
├── src/
│   ├── data_loader.py
│   ├── embedding.py
│   ├── vectorstore.py
│   └── search.py
│
├── data/
├── faiss_store/
├── requirements.txt
└── README.md
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/saiprasanthreddy/Rag-Document-qa.git
cd Rag-Document-qa
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate the environment according to your operating system.

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file:

```text
GROQ_API_KEY=your_api_key_here
```

Never commit your API key to GitHub.

### 5. Add documents

Place supported documents inside the `data/` directory.

### 6. Run the application

```bash
python app.py
```

## 🔍 How It Works

1. Documents are loaded from the data directory.
2. Text is extracted and divided into chunks.
3. Sentence Transformer generates embeddings.
4. FAISS stores the embeddings for similarity search.
5. A user query is converted into an embedding.
6. Relevant document chunks are retrieved.
7. Retrieved context is provided to the LLM.
8. The LLM generates the final answer.

## 📌 Future Improvements

* Conversational memory
* Hybrid keyword + vector search
* Reranking
* Streaming responses
* Web-based interface
* Evaluation using retrieval and generation metrics

## 👨‍💻 Author

**Sai Prasanth Reddy**

[GitHub](https://github.com/saiprasanthreddy) · [LinkedIn](https://www.linkedin.com/in/sai-prasanth-ai/)
