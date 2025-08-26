# FastAPI RAG Project

This is a minimal **FastAPI** project that uses **Elasticsearch** for search and **Ollama/Qwen** for answer generation.

## Setup

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Create a .env file in the project root:

## Example fake file

```
API_PREFIX=/api/v1
ES_URL=http://localhost:9200
ES_INDEX=company_docs
ES_EMBEDDING_DIMS=1024
OLLAMA_URL=http://localhost:11434
LLM_MODEL=qwen2.5:14b-instruct
EMBEDDING_MODEL=nomic-embed-text:latest
TOP_K=8
MAX_TOKENS=512
```

3. Run the app:

```bash
uvicorn app.main:app --reload
```

## Usage

Ask a question:

```bash
curl -X POST "http://localhost:8000/api/v1/query" \
 -H "Content-Type: application/json" \
 -d '{"question": "What is our vacation policy?"}'
```

The API will return an answer with citations from your documents.
