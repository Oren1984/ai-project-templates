# RAG Agent Kit — Project Template (Landing)

**Project type:** Applied AI / RAG Infrastructure  
**Scope:** Secure-by-default, API-first RAG kit (no UI)  
**Owner:** Oren (Oren1984)

---

## Reference repository

- **rag-agent-kit (repo):**  
  https://github.com/Oren1984/rag-agent-kit/tree/main

This document defines the **project-level template** for the RAG Agent Kit —  
a reusable, production-oriented foundation for building RAG-based services.

---

## 1) Purpose

The RAG Agent Kit is designed as a **general-purpose, reusable RAG foundation**:

- API-only (no UI)
- Secure by default
- Modular and extensible
- Suitable for learning, demos, and real-world projects

This template documents:
- Why the project is structured the way it is
- What artifacts must exist
- How to evaluate completeness and readiness

---

## 2) Design philosophy

### API-first
- The kit exposes functionality only via HTTP APIs
- No UI assumptions are made
- Easy to integrate into existing products or workflows

### Secure by default
- The service **will not run** without authentication
- Security middleware is part of the core, not an add-on

### Modular by intent
- Providers, vector stores, connectors, and web search are interchangeable
- Features can be enabled/disabled without refactoring core logic

### Infrastructure-aware (but not infra-bound)
- Docker is the default runtime
- Terraform exists for infra **definition only**
- No automatic production deployment

---

## 3) High-level repository structure

rag-agent-kit/
src/
api/
core/
providers/
embeddings/
retrieval/
vectorstores/
connectors/
websearch/
middleware/
security/
docs/
scripts/
observability/
terraform/
tests/
Dockerfile
docker-compose.yml
.env.example
pyproject.toml
README.md


### Why this structure?

- `src/` → application logic, strictly layered
- `docs/` → human-facing documentation (architecture, usage, security)
- `scripts/` → operational helpers (audit, smoke tests)
- `observability/` → optional tracing/telemetry tooling
- `terraform/` → infra definitions (ECR, etc.), **infra-only**
- Root files → runtime, config, packaging

---

## 4) Core runtime components

### Providers
- Abstract LLM providers (OpenAI, Gemini, Anthropic)
- Unified interface for completion / embeddings

### Vector stores
- Memory store (local/dev)
- pgvector store (production-style)

### Retrieval pipeline
- Query → embedding → retrieval → context assembly
- Deterministic and inspectable

### Connectors
- File-based ingestion
- REST-based ingestion
- Designed for extension

### Optional web search
- Tavily / Serper integrations
- Disabled by default

---

## 5) Security baseline (mandatory)

The following are **non-optional**:

- API key authentication
- CORS restrictions
- Rate limiting
- Security headers
- No secrets in code or repo

Security is treated as a **first-class feature**, not documentation-only.

---

## 6) Observability (optional but recommended)

- OpenTelemetry support
- Phoenix-compatible docker compose
- Explicit observability checks

Observability is:
- Disabled by default
- Enabled explicitly when needed

---

## 7) Infrastructure scope (Terraform)

Terraform exists to:
- Define container registry (ECR)
- Document infra expectations

Terraform does **not**:
- Deploy production services
- Manage secrets
- Replace CI/CD pipelines

This keeps the kit portable and vendor-neutral.

---

## 8) “Run Fast” contract (local)

Every usage of this template must support:

- [ ] Copy `.env.example` → `.env`
- [ ] Set a strong `RAG_API_KEY`
- [ ] `docker compose up -d --build`
- [ ] Access `/docs` endpoint
- [ ] Run smoke test (script or Python)

If this fails, the project is considered incomplete.

---

## 9) Required artifacts

- API running locally
- Smoke test output
- Verification summary
- Security configuration documented
- Optional observability report

Artifacts must be human-readable and reproducible.

---

## 10) Final closure checklist

- [ ] API starts only with valid auth
- [ ] Smoke tests pass
- [ ] Security middleware enabled
- [ ] Docs folder complete
- [ ] No secrets committed
- [ ] Terraform marked as infra-only
- [ ] README clearly explains scope and limits

---

## 11) When to split this template

This file is intentionally a **single landing document**.

Split into multiple templates only if:
- The file grows beyond readability
- Sections become independently reusable
- You need separate security / infra templates

If split, keep this file as the index.