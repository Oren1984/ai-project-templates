# Template — 02_classic_nlp

**Module:** 2  
**Sub-project:** 02 — Classic NLP  
**Task type:** Text classification (TF-IDF + classical models)

---

## Reference repository

- module2-deep-learning-nlp:  
  https://github.com/Oren1984/module2-deep-learning-nlp/tree/main/02_classic_nlp

---

## 1) Purpose

Demonstrate a **strong non-DL baseline** for NLP tasks:
- Feature engineering matters
- Classical models can outperform naive DL
- Clear evaluation and error analysis

---

## 2) Why this structure

- TF-IDF kept explicit and inspectable
- Multiple models trained for comparison
- Results stored in machine-readable format

---

## 3) Expected artifacts

- Baseline + improved models (`.joblib`)
- Confusion matrix figure
- Metrics JSON (baseline vs best)
- Classification report

---

## 4) Evaluation focus

- Precision / Recall tradeoffs
- Class imbalance handling
- Hyperparameter sensitivity

---

## 5) Closure checklist

- [ ] Best model justified vs baseline
- [ ] Metrics clearly compared
- [ ] Failure cases documented
- [ ] Final summary exists