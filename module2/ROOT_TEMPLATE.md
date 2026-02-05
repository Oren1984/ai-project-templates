# Module 2 — ROOT Template (Deep Learning & NLP)

**Module:** Deep Learning & NLP  
**Docs style:** English (single source of truth)  
**Owner:** Oren (Oren1984)

---

## Module repositories (references)

- **module2-deep-learning-nlp (repo):**  
  https://github.com/Oren1984/module2-deep-learning-nlp/tree/main

This ROOT template defines the **conceptual and structural standards** shared across all Module 2 sub-projects:
- 00 — Environment checks
- 01 — Classic Deep Learning (MLP)
- 02 — Classic NLP
- 03 — Hybrid DL + NLP

---

## 1) Purpose

Module 2 focuses on **applied deep learning and NLP**, with an emphasis on:

- Reproducible experiments
- Clear separation between data, code, outputs, and documentation
- Stage-based execution (from framing → training → evaluation → reporting)
- Artifacts-first mindset (models, metrics, figures, reports)

This template ensures that every sub-project:
- Can be reviewed without running code
- Can be reproduced from scratch
- Produces comparable outputs across tasks

---

## 2) High-level module structure

module2-deep-learning-nlp/
00_environment_checks/
01_classic_dl_mlp/
02_classic_nlp/
03_hybrid_dl_nlp/
README.md
requirements.txt
.gitignore


### Why this structure?
- **00** isolates environment validation from ML logic
- **01–03** represent increasing modeling complexity
- Shared conventions allow mental reuse between projects

---

## 3) Standard sub-project structure (why it exists)

<subproject>/
data/
raw/
processed/
doc/
final_summary_en.md
notebooks/
demo.ipynb
outputs/
figures/
models/
reports/
results/
src/
stage0_frame.py
stage1_.py ... stage10_.py
README.md


### Rationale
- `data/` → explicit data lifecycle (raw vs processed)
- `src/` → deterministic, script-based execution
- `notebooks/` → demonstration & explanation only
- `outputs/` → **single source of truth** for results
- `doc/` → final human-readable summary

---

## 4) Stage-based execution philosophy

Stages are **conceptual checkpoints**, not just scripts:

- **Stage 0 — Frame**  
  Problem definition, assumptions, config, metadata.
- **Stage 1 — Load**  
  Dataset loading + integrity checks.
- **Stage 2 — Quick EDA**  
  Distribution sanity, class balance, basic stats.
- **Stage 3 — Preprocess**  
  Cleaning, encoding, splitting.
- **Stage 4 — Baseline**  
  Minimal viable model.
- **Stage 5 — Train**  
  Full training loop.
- **Stage 6 — Evaluate**  
  Metrics + confusion matrix.
- **Stage 7 — Improve**  
  Regularization, tuning, architectural tweaks.
- **Stage 8 — Inference**  
  Prediction logic, sample outputs.
- **Stage 9 — Report**  
  Aggregated results + figures.
- **Stage 10 — Run-all (optional)**  
  Orchestrated execution.

---

## 5) “Run Fast” contract (shared)

Every sub-project must support:

- [ ] Install dependencies
- [ ] Run demo notebook
- [ ] Generate:
  - model artifact
  - metrics JSON
  - at least one evaluation figure
- [ ] Produce a short final report

If this contract fails → project is incomplete.

---

## 6) Final closure checklist (Module 2)

- [ ] Demo notebook runs end-to-end
- [ ] `outputs/` contains all artifacts
- [ ] Final summary exists in `doc/`
- [ ] README explains task + results
- [ ] `.gitignore` excludes heavy or transient files