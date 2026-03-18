# Installation

## Prerequisites

- Python 3.11+
- Azure account (Free tier sufficient)
- Anthropic API key
- Microsoft 365 account (for SharePoint)

## Setup

### 1. Clone the repo
```bash
git clone https://github.com/TON_USERNAME/researchmind.git
cd researchmind
```

### 2. Create virtual environment
```bash
python3.11 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Configure environment variables
```bash
cp .env.example .env
```

Edit `.env` with your credentials :
```bash
ANTHROPIC_API_KEY=your_key
AZURE_SEARCH_ENDPOINT=https://your-service.search.windows.net
AZURE_SEARCH_KEY=your_key
AZURE_TENANT_ID=your_tenant_id
AZURE_CLIENT_ID=your_client_id
AZURE_CLIENT_SECRET=your_client_secret
SHAREPOINT_SITE_ID=your_site_id
```

### 4. Run the app
```bash
docker-compose up
```

Or locally :
```bash
uvicorn app.api.main:app --reload
python ui/gradio_app.py
```