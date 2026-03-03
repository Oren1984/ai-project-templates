# Ticket Triage — Applied AI Templates

This directory contains two production-style applied AI templates
for building an end-to-end IT Ticket Triage system.

---

## Option A — Classical ML + RAG-lite

Path:
option-a_classical-ml_rag-lite/

Characteristics:
- TF-IDF + Logistic Regression
- Lightweight retrieval (vector store)
- FastAPI service
- CPU only
- Minimal dependencies
- Stable demo baseline

Recommended when:
- You want a fast, explainable baseline
- You need quick demo reliability
- You prioritize simplicity

---

## Option B — Deep Learning + RAG

Path:
option-b_dl-rag_distilbert/

Characteristics:
- DistilBERT classifiers (category + urgency)
- SentenceTransformers embeddings
- ChromaDB retrieval
- FastAPI service
- CPU-compatible
- Fallback inference layer

Recommended when:
- You want stronger semantic modeling
- You need scalable NLP architecture
- You aim for a more advanced portfolio showcase

---

## What This Folder Provides

- Clean architecture skeletons
- Clear separation between training and serving
- Docker-ready structure
- Test-ready layout
- Reproducible project contracts

These templates are designed for:
Applied AI Engineering, portfolio projects, and structured demos.