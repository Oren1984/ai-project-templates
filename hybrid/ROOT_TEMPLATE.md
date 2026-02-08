# Hybrid DS + DL Pipeline — ROOT Template (Module 1 + Module 2)

**Module:** Hybrid (Data Science & Classical ML + Deep Learning & NLP)  
**Docs style:** English (single source of truth)  
**Owner:** Oren (Oren1984)

---

## Hybrid repositories (references)

- **hybrid-ds-dl-pipeline (repo):**  
  https://github.com/Oren1984/hybrid-ds-dl-pipeline

This ROOT template captures the shared **conceptual and structural standards** for hybrid projects that combine:
- Module 1 — Data Science & Classical ML
- Module 2 — Deep Learning & NLP

---

## 1) Purpose

This ROOT template defines the **standards and conventions** for hybrid projects
that combine:

- Classical Machine Learning (Module 1 mindset)
- Deep Learning / NLP (Module 2 mindset)

The goal is to reflect **real-world applied AI workflows**:

1. Start simple
2. Establish a measurable baseline
3. Escalate complexity only if justified
4. Compare models objectively
5. Persist results as reproducible artifacts

This is a **template**, not a project.

---

## 2) When to Use This Template

Use this template when:
- You want a Classical ML baseline first
- You may add DL / NLP later
- You want script-first execution
- You want clear artifacts and reports
- You want a reviewable, reproducible pipeline

Do NOT use this template for:
- Agent-based systems
- RAG systems
- Production services
- Research-heavy experimentation

---

## 3) Recommended Repository Structure

{{PROJECT_NAME}}/
├─ src/ # Executable pipeline stages
├─ notebooks/ # Read-only overview notebook
├─ outputs/
│ ├─ models/
│ ├─ results/
│ ├─ reports/
│ └─ figures/
├─ docs/
├─ data/
│ ├─ raw/
│ └─ processed/
├─ requirements.txt
├─ validate_env.py
└─ README.md


---

## 4) Pipeline Stages (Conceptual)

| Stage | Responsibility |
|------|----------------|
| 0 | Frame, metadata, config |
| 1 | Load data |
| 2 | Quick EDA |
| 3 | Preprocess contract |
| 4 | Classical ML baseline |
| 5 | Deep Learning / NLP |
| 6 | Evaluation & comparison |
| 7 | SQL persistence (optional) |
| 8 | Document-style persistence (optional) |
| 10 | Run-all orchestration (demo only) |

---

## 5) Execution Philosophy

- Scripts (`src/`) are the source of truth
- Notebooks are for explanation only
- All outputs are written under `outputs/`
- Metrics are stored as JSON
- Reports are stored as Markdown

---

## 6) Artifacts Contract

Each project created from this template must produce:

### Models
- `outputs/models/*.joblib`

### Metrics
- `outputs/results/classical_metrics.json`
- `outputs/results/dl_metrics.json`
- `outputs/results/final_metrics.json`

### Reports
- `outputs/reports/comparison_report.md`

---

## 7) Notebook Policy

- No training inside notebooks
- Notebooks load existing artifacts only
- Notebooks explain decisions and results

---

## 8) Final Closure Checklist

- [ ] Classical baseline exists
- [ ] DL/NLP added only if justified
- [ ] Metrics are comparable
- [ ] Outputs are reproducible
- [ ] README documents decisions
- [ ] No unnecessary complexity

---

## Final Note

This template is intentionally minimal.

Add complexity **only when results justify it**.