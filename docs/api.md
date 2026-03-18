# API Reference

## Base URL
```
http://localhost:8000
```

## Endpoints

### `POST /query`

Send a natural language query to the Supervisor Agent.

**Request**
```json
{
  "query": "What are the findings on skin microbiome?",
  "mode": "auto"
}
```

**Parameters**
- `query` (string) — the natural language question
- `mode` (string) — `auto`, `rag`, `analytics`, or `hybrid`

**Response**
```json
{
  "answer": "Based on retrieved documents...",
  "sources": ["doc1.pdf", "doc2.pdf"],
  "tool_used": "rag",
  "tokens_used": 1245
}
```

---

### `POST /ingest`

Trigger document ingestion from SharePoint.

**Response**
```json
{
  "status": "success",
  "documents_indexed": 24,
  "duration_seconds": 12.4
}
```

---

### `GET /health`

Health check endpoint.

**Response**
```json
{
  "status": "ok",
  "version": "1.0.0"
}
```

---

### `GET /stats`

Returns platform usage statistics.

**Response**
```json
{
  "total_queries": 142,
  "documents_indexed": 24,
  "avg_response_time_ms": 1823
}
```