# CourtIntel India

AI-powered Indian court intelligence platform starter repo.

## What this repo contains

- `frontend/` — Next.js + Tailwind dashboard UI
- `backend/` — FastAPI API service
- `database/` — PostgreSQL schema
- `docs/` — architecture and legal/safety notes
- `docker-compose.yml` — local Postgres, Redis, OpenSearch, backend, frontend

## Core MVP scope

1. Court directory across India
2. Case watchlists and status placeholders
3. Judgment/order analysis pipeline
4. AI summaries grounded in source text
5. Analytics-ready database design
6. Adapter interface for eCourts, Supreme Court, NJDG, and High Court sources

## Important legal/product note

This starter system is designed for source-grounded research assistance. It should not be marketed as legal advice or outcome prediction. Any AI output must show citations/source references and confidence boundaries.

## Quick start

```bash
cp .env.example .env
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env.local

docker compose up --build
```

Frontend: http://localhost:3000  
Backend API docs: http://localhost:8000/docs

## Real-Time Data Science + Agentic AI Upgrade

This repo now includes a futuristic intelligence layer for real-time court analytics and AI-assisted legal research workflows.

### New backend APIs

- `POST /realtime/events` — ingest normalized court/case events.
- `GET /realtime/events` — inspect latest ingested events.
- `POST /realtime/case-signals` — compute deterministic case features and procedural momentum score.
- `POST /agents/{workflow}` — run prototype Agentic AI workflows: `research`, `monitor_case`, `analyze_case`.
- `GET /agents/models/registry` — list prototype model registry entries.

### New frontend route

- `/realtime` — Real-Time Data Science + Agentic AI overview dashboard.

### New technical modules

- `backend/app/streaming/` — event model and real-time pipeline placeholder.
- `backend/app/data_science/` — feature builder, scoring engine, and model registry.
- `backend/app/agents/` — auditable agents for monitoring, research, and GenAI analysis.
- `docs/REALTIME_AGENTIC_AI.md` — strategic architecture and safety blueprint.

### Safety posture

The system is designed for decision-support intelligence only. It must not provide unsupported legal advice, autonomous legal action, or high-impact legal conclusions without qualified human review.

## Multilingual Chatbot and Upload/Download Upgrade

New modules added:

- Frontend `/chat`: multilingual chatbot agent.
- Frontend `/upload`: AI-powered upload and report download workflow.
- Backend `/chat`: special court-query chatbot agent.
- Backend `/documents/upload`: upload document and generate AI analysis.
- Backend `/documents/download/{file_id}`: download generated AI report.

See `docs/MULTILINGUAL_CHATBOT_UPLOADS.md` for production guidance.
