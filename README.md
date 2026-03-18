# ResearchMind 🔬

**Agentic RAG Platform — Chat with your research documents and analytics data**

[![Deploy Documentation](https://github.com/hackSOKA/researchmind/actions/workflows/ci.yml/badge.svg)](https://github.com/hackSOKA/researchmind/actions/workflows/ci.yml)

> ResearchMind is a production-grade AI platform that gives research teams a single conversational interface to query both their documents and analytical data simultaneously — powered by Claude (Anthropic), Azure AI Search, and LangGraph.

## 📚 Documentation

**[https://hacksoka.github.io/researchmind/](https://hacksoka.github.io/researchmind/)**

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| LLM | Anthropic Claude Sonnet |
| Orchestration | LangGraph |
| Vector Search | Azure AI Search |
| Embeddings | Sentence Transformers |
| SharePoint | Microsoft Graph API |
| API | FastAPI |
| UI | Gradio |
| Containers | Docker |

## 🚀 Quick Start
```bash
git clone https://github.com/hackSOKA/researchmind.git
cd researchmind
python3.11 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# Fill in your credentials in .env
uvicorn app.api.main:app --reload
```

## 📄 License

MIT