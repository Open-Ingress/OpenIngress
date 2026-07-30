# Self-hosting OpenIngress

Run the crawl + break-point engine and dashboard locally. Bring your own LLM API key (required).
OSS scope: **live public sites** (paste a URL). Authenticated / internal tools are enterprise.

## Quick start

```bash
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env

# Required — add your key in backend/.env:
# LLM_API_KEY=sk-...

make install   # creates venv, pip install, Playwright Chromium, npm install
make backend   # terminal 1 → http://127.0.0.1:5055
make frontend  # terminal 2 → http://localhost:5175
```

Open `http://localhost:5175` → **New** → enter a public site URL → review coverage and break points.

### Prerequisites

- **Python 3.10+** (Makefile prefers `python3.10`, falls back to `python3`)
- **Node 18+** for the Vite UI
- Network access once for `playwright install chromium` (included in `make install`)

If Chromium is missing later: `cd backend && . .venv/bin/activate && python -m playwright install chromium`

On Linux you may also need: `python -m playwright install-deps chromium`

## Required env

| Variable | Where | Notes |
|----------|-------|-------|
| `LLM_API_KEY` | `backend/.env` | Required for run create + exploration |
| `AUTH_DISABLED=1` | `backend/.env` | Default on — local auth off |
| `BILLING_DISABLED=1` | `backend/.env` | Default on — billing routes inert |
| `VITE_AUTH_DISABLED=1` | `frontend/.env` | Must match backend for local OSS |
| `VITE_API_URL` | `frontend/.env` | Points at local API |

Optional: `LLM_BASE_URL`, `LLM_MODEL_NAME`, Azure OpenAI vars — see **LLM providers** below.

## LLM providers

OpenIngress talks to an **OpenAI-compatible** chat API (`/chat/completions`). Set these in `backend/.env`, then restart the backend.

| Variable | Purpose |
|----------|---------|
| `LLM_PROVIDER` | `openai` (default) or `azure` |
| `LLM_API_KEY` | API key |
| `LLM_BASE_URL` | Chat completions base URL |
| `LLM_MODEL_NAME` | Model id |

### OpenAI

```bash
LLM_PROVIDER=openai
LLM_API_KEY=sk-...
LLM_BASE_URL=https://api.openai.com/v1
LLM_MODEL_NAME=gpt-4o-mini
```

### Google Gemini (OpenAI-compatible endpoint)

```bash
LLM_PROVIDER=openai
LLM_API_KEY=your-gemini-api-key
LLM_BASE_URL=https://generativelanguage.googleapis.com/v1beta/openai/
LLM_MODEL_NAME=gemini-flash-latest
```

### Azure OpenAI

```bash
LLM_PROVIDER=azure
AZURE_OPENAI_API_KEY=...
AZURE_OPENAI_ENDPOINT=https://YOUR_RESOURCE.openai.azure.com/
AZURE_OPENAI_DEPLOYMENT=your-deployment-name
```

You can also set `LLM_API_KEY` / `LLM_MODEL_NAME` to match the deployment if your setup still reads the generic vars.

### Other OpenAI-compatible hosts

Any gateway that exposes `/chat/completions` works (OpenRouter, Ollama with an OpenAI shim, company proxies, etc.):

```bash
LLM_PROVIDER=openai
LLM_API_KEY=...
LLM_BASE_URL=https://your-host.example/v1
LLM_MODEL_NAME=your-model-id
```

## Crawl defaults

- Max depth: **3**
- Max pages: **100**

Tune via run payload `max_pages` if needed.

## Docker

See root `Dockerfile` for a containerized backend (Playwright image + Gunicorn). Frontend: `cd frontend && npm run build`. Default job mode is `inline` (`JOB_EXECUTION_MODE`).
