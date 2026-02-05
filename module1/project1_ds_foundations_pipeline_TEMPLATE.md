# Template — ds-foundations-pipeline (Project)

**Project type:** Module 1 / DS pipeline (foundations-style)  
**Goal:** End-to-end DS pipeline with clear stages + artifacts + showcase notebook.  
**Reference style:** Similar conventions to Module 1 repos.

---

## Related repositories (examples)

- module1-ds-classical-ml: https://github.com/Oren1984/module1-ds-classical-ml/tree/main

---

## 1) Folder tree (expected)

{{REPO_NAME}}/
docs/
STAGES_EN.md
STAGE10_SQL_EN.md
notebooks/
01_pipeline_showcase.ipynb
reports/figures/ # legacy style (allowed)
src/
README.md
requirements.txt
.gitignore


> Note: New projects should prefer `outputs/` instead of `reports/figures/`.  
> Keep this structure as-is if matching the original repo.

---

## 2) Run Fast (local)

- [ ] `pip install -r requirements.txt`
- [ ] Open: `notebooks/01_pipeline_showcase.ipynb`
- [ ] Run all cells
- [ ] Verify:
  - `reports/figures/*.png` exists (or outputs)
  - Metrics artifacts produced (json/csv)

---

## 3) Stage outputs (minimum)

**Must produce:**
- EDA plots (histograms + correlation heatmap)
- Evaluation plots (confusion matrix + ROC/PR)

**Optional (if included):**
- Unsupervised plots (elbow + silhouette)
- DR plots (PCA + t-SNE)

**Recommended naming:**
- `stage2_*`
- `stage6_*`
- `stage8_*`
- `stage9_*`

---

## 4) Documentation requirements

- `docs/STAGES_EN.md` includes:
  - dataset
  - target
  - split method
  - main metric(s)
  - outputs list per stage
- `docs/STAGE10_SQL_EN.md` includes:
  - schema overview
  - example queries
  - how to reproduce

---

## 5) Final closure checklist

- [ ] `README.md` includes:
  - What this project does
  - Quick start
  - Key results (numbers)
  - Key figures (links)
- [ ] figures exist and are committed (small pngs only)
- [ ] no raw datasets committed unless small and allowed
