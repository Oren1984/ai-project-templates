# Template — ds-mini-pipeline (Project)

**Project type:** Module 1 / Mini pipeline  
**Goal:** Lightweight DS pipeline with strict artifacts under `outputs/`.

---

## Related repositories (examples)

- module1-ds-classical-ml: https://github.com/Oren1984/module1-ds-classical-ml/tree/main

---

## 1) Folder tree (expected)

{{REPO_NAME}}/
docs/
STAGES_EN.md
STAGE10_SQL_EN.md
(optional) STAGE11_MONGO_EN.md
notebooks/
01_pipeline_showcase.ipynb
02_pipeline_report.ipynb
outputs/
figures/
models/
reports/
results/
src/
env/ # optional (helpers / notes)
.env.example
config.py
db.py
validate_env.py
requirements.txt
README.md
.gitignore


---

## 2) Run Fast (local)

- [ ] `pip install -r requirements.txt`
- [ ] `python validate_env.py`
- [ ] Run: `notebooks/01_pipeline_showcase.ipynb`
- [ ] Run: `notebooks/02_pipeline_report.ipynb` (generates final report)
- [ ] Verify outputs exist under `outputs/`

---

## 3) Required artifacts

### Figures
- `outputs/figures/stage2_hist.png`
- `outputs/figures/stage2_corr.png`
- `outputs/figures/stage6_confusion_matrix.png`
- `outputs/figures/stage6_roc_curve.png`

**Optional**
- `outputs/figures/stage2_5_pca.png`
- `outputs/figures/stage8_elbow.png`
- `outputs/figures/stage8_silhouette.png`

### Models
- `outputs/models/stage4_baseline.joblib`
- (optional) `outputs/models/stage7_best_model.joblib`

### Results / Reports
- `outputs/results/*.json` (metrics + metadata)
- `outputs/reports/stage5_model_compare.csv`
- `outputs/reports/report.md` (or generated notebook report)

---

## 4) DB / ENV conventions

- `.env.example` includes only placeholders:
  - DB host, port, user, password, database
- `validate_env.py` must fail clearly if env is missing
- `db.py` contains minimal connector logic (no secrets inside code)

---

## 5) Documentation requirements

- `docs/STAGES_EN.md` maps:
  - stage → input → output file(s)
- SQL/Mongo docs include:
  - minimal schema
  - reproduction steps
  - example query snippets

---

## 6) Final closure checklist

- [ ] outputs are complete (figures/models/results)
- [ ] report notebook runs end-to-end
- [ ] `.gitignore` excludes raw data, checkpoints, local env folders
- [ ] README has “Results” section:
  - main metric(s)
  - best model
  - links to key figures