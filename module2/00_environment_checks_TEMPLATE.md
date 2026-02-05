# Template — 00_environment_checks

**Module:** 2  
**Sub-project:** 00 — Environment checks  
**Goal:** Validate that the machine is ready for DL/NLP work.

---

## Reference repository

- module2-deep-learning-nlp:  
  https://github.com/Oren1984/module2-deep-learning-nlp/tree/main/00_environment_checks

---

## 1) Purpose

This sub-project exists to **fail early**.

Before any modeling:
- Verify Python, PyTorch, CUDA
- Detect GPU availability
- Measure basic performance

No ML logic should exist here.

---

## 2) Expected structure

00_environment_checks/
Test_PyTorch_Setup_module2.ipynb
GPU_performance_module2.ipynb
README.md


---

## 3) What must be validated

- Python version
- PyTorch import
- CUDA availability (if applicable)
- GPU device name
- Basic tensor operations

Optional:
- Simple benchmark comparison (CPU vs GPU)

---

## 4) Run Fast

- [ ] Install module dependencies
- [ ] Run `Test_PyTorch_Setup_module2.ipynb`
- [ ] Run `GPU_performance_module2.ipynb` (optional)
- [ ] Update README with:
  - device summary
  - CUDA status
  - short conclusion

---

## 5) Closure checklist

- [ ] Environment issues documented
- [ ] Screenshots or outputs summarized
- [ ] No training or datasets included