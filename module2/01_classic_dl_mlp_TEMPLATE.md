# Template — 01_classic_dl_mlp

**Module:** 2  
**Sub-project:** 01 — Classic Deep Learning (MLP)  
**Task type:** Image classification (e.g., FashionMNIST)

---

## Reference repository

- module2-deep-learning-nlp:  
  https://github.com/Oren1984/module2-deep-learning-nlp/tree/main/01_classic_dl_mlp

---

## 1) Purpose

Introduce deep learning fundamentals:
- Tensor flow through a network
- Training loop
- Overfitting vs regularization
- Evaluation beyond accuracy

This project serves as the **DL baseline** for the module.

---

## 2) Why this structure

- Dataset is simple → focus on modeling
- MLP chosen → minimal architecture complexity
- Clear separation between:
  - training logic
  - evaluation
  - reporting

---

## 3) Expected artifacts

### Models
- `best_model.pt`

### Figures
- Accuracy & loss curves
- Confusion matrix
- Sample predictions grid

### Results
- Training history
- Final metrics JSON
- Short text summary

---

## 4) Quality gates

- [ ] Model trains from scratch
- [ ] Metrics are reproducible
- [ ] Overfitting behavior is observable
- [ ] Figures match reported numbers

---

## 5) Closure checklist

- [ ] Demo notebook runs
- [ ] Outputs folder complete
- [ ] Final summary written
- [ ] README highlights results + insights