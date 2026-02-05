# Module 1 — ROOT Template (DS & Classical ML)

**Module:** Data Science & Classical ML  
**Docs style:** English (single source of truth)  
**Owner:** Oren (Oren1984)

---

## Module projects (references)

- **module1-ds-classical-ml (repo):** https://github.com/Oren1984/module1-ds-classical-ml/tree/main

> This template hub also includes two “pipeline-style” project templates that reflect my Module 1 structure standards.

---

## 1) Purpose

This ROOT template defines **shared conventions** for Module 1 projects:
- Consistent repo structure
- Stage-based workflow (Stage 0 → Stage 10/11 optional)
- Standardized outputs and reporting artifacts
- Minimal and reliable “Run Fast” flow

---

## 2) Expected repository structure (common)

> Each project may have variations, but aim to keep these conventions stable.

{{REPO_NAME}}/
docs/
STAGES_EN.md
(optional) STAGE10_SQL_EN.md
(optional) STAGE11_MONGO_EN.md
notebooks/
01_pipeline_showcase.ipynb
(optional) 02_pipeline_report.ipynb
outputs/ # preferred for new projects
figures/
models/
reports/
results/
src/
requirements.txt
(optional) .env.example
(optional) validate_env.py
README.md
.gitignore


### Artifact conventions
- `outputs/figures/` → plots (png/jpg)
- `outputs/models/` → trained models (`.joblib`)
- `outputs/reports/` → markdown/csv summaries
- `outputs/results/` → metrics + metadata (`.json`, `.txt`)
- Prefer a single “source of truth” for results: JSON + short report md

---

## 3) Stage workflow standard (recommended)

Use a stage map that is readable and consistent:

- **Stage 0 — Meta / Setup**  
  Problem framing, dataset info, environment validation, baseline config.
- **Stage 1 — Load**  
  Ingest raw data, basic checks.
- **Stage 2 — Quick EDA**  
  Distributions, correlation, missing values, first insights.
- **Stage 3 — Preprocess**  
  Cleaning, split, feature engineering, scaling/encoding.
- **Stage 4 — Baseline model**  
  Minimal model + basic evaluation.
- **Stage 5 — Model comparison**  
  Multiple models, simple selection, table output.
- **Stage 6 — Evaluation**  
  Confusion matrix, ROC/PR, threshold notes.
- **Stage 7 — Tuning (optional)**  
  Hyperparam tuning, best model artifact.
- **Stage 8 — Unsupervised (optional)**  
  KMeans, elbow, silhouette.
- **Stage 9 — Dimensionality reduction (optional)**  
  PCA / t-SNE plots.
- **Stage 10 — SQL layer (optional)**  
  Save curated dataset + example queries.
- **Stage 11 — Mongo layer (optional)**  
  Load results/metadata into Mongo.

---

## 4) “Run Fast” checklist (minimum)

- [ ] Create & activate venv
- [ ] `pip install -r requirements.txt`
- [ ] (if exists) `python validate_env.py`
- [ ] Run notebook demo OR `python -m src.<entrypoint>`
- [ ] Confirm outputs created under `outputs/`
- [ ] Update README with final results

---

## 5) Template placeholders

Replace these fields in copied templates:
- `{{PROJECT_NAME}}`
- `{{REPO_URL}}`
- `{{DATASET}}`
- `{{TARGET}}`
- `{{METRIC_PRIMARY}}`
- `{{PYTHON_VERSION}}`

---

## 6) Final closure checklist (Module 1)

- [ ] Folder tree matches the template (or differences are documented)
- [ ] Outputs are reproducible from a clean environment
- [ ] Key figures exist (EDA + evaluation)
- [ ] Metrics JSON exists
- [ ] A short final report exists (`report.md` or README section)
- [ ] `.gitignore` excludes heavy artifacts (raw data, big models)
