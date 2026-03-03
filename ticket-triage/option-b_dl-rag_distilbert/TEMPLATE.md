# AI Ticket Triage (DL + RAG) — Project Template (Module 2 + RAG)

Project type: End-to-End Applied AI (Deep Learning + Retrieval)
Module: Module 2 (Deep Learning & NLP) + RAG retrieval
Scope: CPU-compatible, Docker-ready, testable system with fallback inference
Owner: Oren (Oren1984)

---

## Reference repository

- ai-ticket-triage-dl-rag (repo):
  https://github.com/Oren1984/ai-ticket-triage-dl-rag :contentReference[oaicite:19]{index=19}

This template defines a complete hybrid system:
**DistilBERT classifiers + ChromaDB retrieval + FastAPI service + tests + Docker**, designed to run on :contentReference[oaicite:20]{index=20}:contentReference[oaicite:21]{index=21}

---

## 1) Overview

End-to-end IT support ticket triage system combining:

- **DistilBERT** classification (Category + Urgency)
- **RAG retrieval** (ChromaDB + SentenceTransformers)
- **FastAPI** REST API + demo UI
- Dockerized, test-covered, CPU-compatible :contentReference[oaicite:22]{index=22}

---

## 2) Task Definition

Input:
- Ticket text (+ optional metadata)

Outputs:
- category prediction
- urgency prediction
- Top-K runbook retrieval results
- structured response payload (for UI/API clients) :contentReference[oaicite:23]{index=23}

---

## 3) System Scope (Hybrid)

Hybrid by design:
- DL/NLP modeling + retrieval pipeline + service runtime must be documented as one system. :contentReference[oaicite:24]{index=24}

Non-goals:
- No GPU requirement
- Avoid production infra automation in-template (keep portable)
- Keep demo reliable via fallback inference if training artifacts missing :contentReference[oaicite:25]{index=25}

---

## 4) Design Rationale

- DL classifiers improve semantic understanding vs classical baseline
- Retrieval grounds responses in runbooks (inspectable, deterministic)
- API-first architecture ensures integration readiness
- “Fail-safe demo” policy: fallback logic prevents broken demos :contentReference[oaicite:26]{index=26}

---

## 5) Why Each Component Was Chosen

- **DistilBERT**: strong lightweight transformer for CPU-friendly NLP
- **SentenceTransformers**: efficient embedding generation for retrieval
- **ChromaDB**: simple, local-first vector store for demo workflows
- **FastAPI**: clean contracts + Swag:contentReference[oaicite:27]{index=27}*Docker Compose**: one-command environment parity :contentReference[oaicite:28]{index=28}

---

## 6) Pipeline Stages (End-to-End)

Stage 0 — Dataset contract & mapping  
- Define label space (category, urgency) and splits

Stage 1 — Training  
- Train DistilBERT classifiers (category + urgency)
- Save checkpoints and evaluation summaries

Stage 2 — Embeddings + Index  
- Build embeddings for runbooks
- Persist ChromaDB index

Stage 3 — Serving  
- Predict category + urgency
- Retrieve Top-K runbooks
- Generate structured response

Stage 4 — Reliability Layer  
- Fallback inference path for demo reliability (when artifacts unavailable) :contentReference[oaicite:29]{index=29}

Stage 5 — Validation  
- Tests (unit/integration) + docker sanity + smoke checks :contentReference[oaicite:30]{index=30}

---

## 7) Recommended Repository Structure

ai-ticket-triage-dl-rag/
├─ app/                 # FastAPI app (routers, services, schemas)
├─ training/            # training code / configs
├─ scripts/             # helpers: build index, reports, smoke tests
├─ knowledge_base/      # runbooks (markdown)
├─ data/                # local data (gitignored as needed)
├─ models/              # trained artifacts / checkpoints
├─ reports/             # eval + run summaries
├─ tests/               # pytest (unit + integration)
├─ docs/                # technical docs (training notes, mapping, reports)
├─ .env.example
├─ Dockerfile
├─ docker-compose.yml
├─ requirements.txt
└─ README.md :contentReference[oaicite:31]{index=31}

---

## 8) Results & Artifacts (Contract)

### Models
- `models/` contains:
  - classifier checkpoints
  - tokenizer/config (if applicable)

### Retrieval
- persisted ChromaDB index OR rebuild script

### Metrics & Reports
- classification metrics for category + urgency
- retrieval sanity (Top-K examples)
- end-to-end sample outputs (API payload examples)

### Demo Reliability
- explicit note on fallback behavior and how to verify it :contentReference[oaicite:32]{index=32}

---

## 9) Notebook Usage Policy

- No critical logic lives only in notebooks
- Notebooks (if any) are explanatory: load artifacts, show results
- Scripts/services remain the source of truth :contentReference[oaicite:33]{index=33}

---

## 10) Testing & CI/CD (Minimum)

Minimum expectations:
- `pytest -q` runs locally :contentReference[oaicite:34]{index=34}
- Docker build succeeds in CI
- Smoke test:
  - compose up
  - hit `/health`
  - hit `/docs`
  - hit `/triage` with a sample ticket

Recommended CI jobs:
- unit tests
- docker build
- lightweight integration smoke (compose + curl)

---

## 11) Security Baseline (Minimum)

- `.env.example` present
- no secrets committed
- basic CORS policy
- dependency constraints for reproducibility

---

## 12) “Run Fast” Contract (Local)

Must support:
1) `git clone …`
2) `docker compose up --build`
3) open:
   - API: `/`
   - Swagger: `/docs`
   - UI: `/ui` :contentReference[oaicite:35]{index=35}
4) run `pytest -q` :contentReference[oaicite:36]{index=36}

If this fails — the project is considered incomplete.

---

## Final Notes

This template is intentionally focused on an applied, testable, demo-ready system.
Add complexity only when it improves measurable outcomes or usability. :contentReference[oaicite:37]{index=37}