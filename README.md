# RAG-Pipeline

A lightweight Retrieval-Augmented Generation (RAG) pipeline for document search, embedding, and summarization using Faiss, Sentence Transformers, and Groq.

Developed by UV.

The installation and setup instructions in this README are provided by UV.

## Overview

This repository ingests documents from the `data` directory, builds a FAISS vector index from text embeddings, and performs query-driven retrieval plus summarization using a Groq language model.

Key features:

- Supports PDF, TXT, CSV, XLSX, DOCX, and JSON document loading
- Splits documents into semantic chunks before embedding
- Builds and persists a FAISS vector store with metadata
- Queries the vector store and summarizes results via a Groq LLM
- Organized modular code in `src/` for loader, embedding, vector store, and search logic

## Repository Structure

- `app.py` - main entrypoint for running the RAG pipeline
- `main.py` - simple placeholder script
- `src/data_loader.py` - document ingestion and loading
- `src/embedding.py` - chunking and embedding pipeline
- `src/vectorstore.py` - FAISS index management and nearest neighbor search
- `src/search.py` - retrieval + LLM summarization wrapper
- `data/` - source documents and vector store artifacts
- `faiss_store/` - persisted FAISS index and metadata files

## Requirements

- Python 3.14+
- `pip` package manager
- Recommended: virtual environment

## Installation

```powershell
cd "c:\Users\SAI\Desktop\data-Science\projects\RAG-pipline"
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Alternatively, install via `pyproject.toml`:

```powershell
python -m pip install --upgrade pip
python -m pip install .
```

## Environment

Create a `.env` file in the project root with your Groq API key:

```text
GROQ_API_KEY=your_groq_api_key_here
```

> Do not commit secret keys to source control.

## Usage

1. Place your supported documents under `data/`.
   - `data/pdf/`
   - `data/text_files/`
   - `data/` subfolders for CSV, XLSX, DOCX, JSON

2. Run the pipeline:

```powershell
python app.py
```

The application will:

- load documents from the `data` directory
- build or load the FAISS index in `faiss_store`
- perform a query and summarize the retrieved context

## Customization

- `src/embedding.py` controls chunk size and overlap
- `src/vectorstore.py` controls the FAISS persistence directory and embedding model
- `src/search.py` controls the retrieval strategy and Groq summarization prompt

## Supported File Types

- PDF: `.pdf`
- Text: `.txt`
- CSV: `.csv`
- Excel: `.xlsx`
- Word: `.docx`
- JSON: `.json`

## Troubleshooting

- If no documents are found, verify files exist under `data/` and are of a supported type.
- If FAISS reload fails, delete `faiss_store/` and rerun `python app.py` to rebuild.
- If the Groq client fails, verify `GROQ_API_KEY` is set and the key is valid.

## Notes

- `main.py` is a placeholder and prints `Hello from rag-pipline!`.
- The actual query flow exists in `app.py` and `src/search.py`.
- The project currently depends on `langchain`, `sentence-transformers`, `faiss-cpu`, `chromadb`, and Groq.

## License

Add your license information here.
