# AI Ticket Triage Demo — Project Template (Module 1 + RAG-lite)

Project type: Applied AI Demo (Classical ML + Retrieval)
Module: Module 1 (Data Science & Classical ML) + RAG-style retrieval (no external LLM)
Scope: Lean, CPU-fast, Dockerized, demo-ready
Owner: Oren (Oren1984)

---

## Reference repository

- ai-ticket-triage-demo (repo):
  https://github.com/Oren1984/ai-ticket-triage-demo :contentReference[oaicite:1]{index=1}

This template defines the **documentation + structure contract** for a lightweight end-to-end ticket triage system:
**Classical ML classifier + runbook retrieval + FastAPI service + tests + Docker**. :contentReference[oaicite:2]{index=2}

---

## 1) Overview

This project demonstrates a complete applied AI workflow:

- Ticket text classification (TF-IDF + Logistic Regression)
- Retrieval of relevant runbooks (ChromaDB / vector store)
- Template-based response generation (no external LLM key required)
- FastAPI REST API + Swagger + simple UI
- Fully containerized and test-covered :contentReference[oaicite:3]{index=3}

---

## 2) Task Definition

Input:
- A support ticket text (optionally with metadata like product/service)

Outputs:
- Predicted category (primary)
- Urgency (optional / placeholder or rule-based)
- Top-K runbook recommendations
- Structured JSON response for downstream use :contentReference[oaicite:4]{index=4}

---

## 3) System Scope (Hybrid)

Why Hybrid?
- Combines **ML classification** + **retrieval system** + **backend service** as one coherent pipeline.
- Must be documented end-to-end (system thinking), not as isolated scripts. :contentReference[oaicite:5]{index=5}

Non-goals:
- No LLM calls required
- No GPU requirement
- No production infra automation (this is a demo template)

---

## 4) Design Rationale

Principles:
- “S:contentReference[oaicite:6]{index=6}assical baseline first
- Deterministic, explainable pipeline
- Reproducibility: artifacts + reports + tests
- Demo reliability: avoid dependencies on external keys/services :contentReference[oaicite:7]{index=7}

---

## 5) Why Each Component Was Chosen

- **TF-IDF + Logistic Regression**: strong baseline for text classification; fast on CPU
- **Train-only EDA balancing**: reduces leakage risk while improving robustness :contentReference[oaicite:8]{index=8}
- **ChromaDB retrieval**: simple RAG-style runbook lookup (Top-K)
- **FastAPI**: clean API contract + easy docs (Swagger)
- **Docker Compose**: one-command demo environment :contentReference[oaicite:9]{index=9}

---

## 6) Pipeline Stages (End-to-End)

Stage 0 — Data & splits  
- Define dataset mapping and stratified split (train/val/test)

Stage 1 — Preprocess + Augmentation (train-only)  
- Apply EDA only on train set (no leakage)

Stage 2 — Train baseline classifier  
- Train TF-IDF + Logistic Regression
- Save model artifacts

Stage 3 — Index knowledge base  
- Ingest runbooks into vector store (ChromaDB)

Stage 4 — Serve  
- `/triage` orchestrates: classify → retrieve → response template

Stage 5 — Validate  
- Unit tests + integration tests + docker build sanity :contentReference[oaicite:10]{index=10}

---

## 7) Recommended Repository Structure

ai-ticket-triage-demo/
├─ app/                 # FastAPI app (routers, services, schemas)
├─ scripts/             # prepare/train/ingest utilities
├─ knowledge_base/      # runbooks (markdown)
├─ models/              # serialized ML artifacts (+ archive if needed)
├─ reports/             # evaluation reports, run summaries
├─ tests/               # pytest (unit + integration)
├─ docs/                # design/architecture notes (optional but recommended)
├─ .env.example
├─ Dockerfile
├─ docker-compose.yml
├─ requirements.txt
├─ README.md
└─ RUN.md / DEMO.md :contentReference[oaicite:11]{index=11}

---

## 8) Results & Artifacts (Contract)

Artifacts must be reproducible and human-readable:

### Models
- `models/*.joblib` (or equivalent)

### Retrieval Index
- persisted ChromaDB directory (if used) OR rebuild script

### Metrics
- `reports/*.json` or `reports/*.md` with:
  - accuracy, macro-F1 on test
  - validation-vs-test sanity check :contentReference[oaicite:12]{index=12}

### Demo Validation
- “Docker build OK”
- “Endpoints OK”
- “pytest passing” :contentReference[oaicite:13]{index=13}

---

## 9) Notebook Usage Policy

- Scripts/services are the source of truth
- Notebooks (if any) are **read-only**: exploration and explanation only
- No training logic locked inside notebooks :contentReference[oaicite:14]{index=14}

---

## 10) Testing & CI/CD (Minimum)

Minimum expectations:
- `pytest` runnable locally
- Docker build test in CI
- Basic smoke test hitting `/health` and `/triage` :contentReference[oaicite:15]{index=15}

Recommended GitHub Actions jobs:
- lint (optional)
- unit tests
- docker build
- integration smoke (compose up + curl health)

---

## 11) Security Baseline (Minimum)

- `.env.example` provided
- No secrets committed
- CORS configured appropriately (even for demo)
- Dependency sanity (pin or constrain key pack:contentReference[oaicite:16]{index=16}Contract (Local)

Must support:
1) copy `.env.example` → `.env`
2) `docker compose up --build`
3) open:
   - `/docs` (Swagger)
   - `/health`
4) run `pytest` :contentReference[oaicite:17]{index=17}

If this fails — the project is considered incomplete.

---

## Final Notes

This template is intentionally lean.
Add complexity only when the baseline proves value. :contentReference[oaicite:18]{index=18}