# Usage

## Starting the Platform
```bash
# Activate virtual environment
source .venv/bin/activate

# Start the API
uvicorn app.api.main:app --reload

# In a second terminal, start the UI
python ui/gradio_app.py
```

Open your browser at `http://localhost:7860`

## Querying Documents (RAG)

Type any question related to your research documents :
```
"What are the latest findings on skin microbiome and cosmetic formulation?"
"Summarize the safety assessment for UV filter X"
"What does the OECD report say about nuclear waste management?"
```

The RAG engine will retrieve the most relevant chunks from SharePoint and generate a sourced answer.

## Querying Analytics Data

Ask data-driven questions in natural language :
```
"What is the average experiment success rate per research team?"
"Show me the top 5 compounds tested in Q1 2025"
"Compare results between lab A and lab B"
```

The Analytics Agent translates your question into pandas operations and returns structured insights.

## Combined Queries

ResearchMind shines when combining both sources :
```
"Based on the latest reports and our experimental data,
which compounds show the most promise for UV protection?"
```

The Supervisor Agent automatically routes to both tools and synthesizes a unified answer.

## Ingesting New Documents

New documents added to SharePoint are automatically ingested on the next pipeline run :
```bash
python -m app.rag.pipeline
```