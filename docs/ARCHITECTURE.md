# CourtIntel India Architecture

## Product goal

Build a source-grounded court intelligence platform for India that lists courts, tracks official case signals, and uses AI for explainable legal research assistance.

## Non-goals for MVP

- No legal advice automation
- No guaranteed outcome prediction
- No captcha bypassing or unauthorized scraping
- No hidden model training on sensitive case/user data

## System layers

### 1. Frontend

- Next.js app
- Public pages: landing, court directory
- Authenticated future pages: watchlists, case dashboards, analytics

### 2. Backend API

- FastAPI
- Courts API
- Cases API
- Search API
- AI document analysis API

### 3. Data ingestion

Use source adapters for each source family:

- eCourts services
- Supreme Court services
- High Court services
- NJDG pendency dashboards
- Judgment/order repositories

Each adapter should implement:

- fetch courts
- fetch case status
- fetch recent documents
- fetch pendency snapshots where available

### 4. Data storage

- PostgreSQL: source-of-record structured data
- OpenSearch: full-text and semantic-ready search
- Redis: queues/cache/watchlist event state

### 5. AI engine

Start deterministic, then add LLM capabilities:

- summarization
- issue extraction
- statutes/citations extraction
- procedural timeline generation
- similar-case clustering
- risk flags and confidence boundaries

Every AI answer must be grounded in source spans.

## Production priorities

1. Source provenance
2. Audit logs
3. Role-based access control
4. Data retention policy
5. Human review gates
6. Legal/compliance review
7. Observability for ingestion health
