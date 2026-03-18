# Architecture

## Overview
```
Gradio UI
    ↓
FastAPI Backend
    ↓
LangGraph Supervisor Agent
    ├── RAG Tool → Azure AI Search + Claude
    └── Analytics Tool → Pandas Agent + Claude
```

## Components

### Supervisor Agent
LangGraph state machine that decides which tool to invoke based on the user query. Supports multi-step reasoning and tool chaining.

### RAG Pipeline
1. Documents ingested from SharePoint via Microsoft Graph API
2. Split into chunks with overlap
3. Embedded with Sentence Transformers (local, free)
4. Indexed in Azure AI Search
5. Hybrid search (semantic + keyword) at query time
6. Reranking for precision
7. Claude generates final answer from retrieved context

### Analytics Agent
LangChain Pandas agent that translates natural language into Python/pandas operations over CSV datasets.

## Data Flow
```
SharePoint → Graph API → Chunking → Embedding → Azure AI Search
                                                       ↓
User Query → Supervisor → RAG Tool → Hybrid Search → Claude → Answer
                       → Analytics Tool → Pandas → Claude → Answer
```