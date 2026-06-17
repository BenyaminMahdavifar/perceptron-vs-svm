# Perceptron vs SVM — Margin & Overfitting

> An interactive visual explanation of why SVM generalizes better than a plain Perceptron — built from a Python notebook into a live scientific dashboard.

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-4f8eff?style=flat-square&logo=github)](https://benyaminmahdavifar.github.io/perceptron-vs-svm/docs/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Notebook](https://img.shields.io/badge/Jupyter-notebook-orange?style=flat-square&logo=jupyter)](Preceptron_vs_SVM.ipynb)

---

## Overview

Both Perceptron and SVM can correctly separate linearly separable data. The difference is *what they optimize for*:

- **Perceptron** stops as soon as every training point is on the correct side — no matter how close the boundary is to the data.
- **SVM** goes further: it finds the boundary that maximises the *margin* — the perpendicular gap between the two closest parallel support hyperplanes.

This repository contains a Python notebook with numerical simulations, and an interactive GitHub Pages dashboard that turns those simulations into a hands-on visual experience.

---

## Live Dashboard

**[benyaminmahdavifar.github.io/perceptron-vs-svm/docs/](https://benyaminmahdavifar.github.io/perceptron-vs-svm/docs/)**

### Interactive features

| Section | What you can do |
|---|---|
| **Decision Boundary** | Click to place Class +1 / −1 points; drag them; watch both boundaries update in real time |
| **Outlier test** | Add an outlier and observe how the Perceptron boundary shifts while SVM stays stable |
| **C regularisation** | Slide C from soft to hard margin and see the margin band change |
| **Margin geometry** | Static diagram explaining γ = 2/‖w‖ with support vectors highlighted |
| **Noise robustness** | Drag σ from 0 → 1.5 and watch both accuracy curves drop at different rates |

---

## Key Results

| Quantity | Perceptron | SVM |
|---|---|---|
| Optimisation goal | Correct classification | Max-margin classification |
| Sensitivity to outliers | High | Low (only support vectors matter) |
| Explicit probability model | No | No (discriminative) |
| Generalisation bound | Depends on convergence | Tied directly to margin width γ |
| Training complexity | O(n) per epoch | O(n²) – O(n³) for exact solver |

The margin width γ = 2/‖w‖ directly controls the VC-theory generalisation error bound — a larger margin means a tighter bound on test error.

---

## Notebook

`Preceptron_vs_SVM.ipynb` contains:

- Synthetic 2-class dataset generation with a deliberate outlier
- Perceptron training (scikit-learn) and decision boundary visualisation
- SVM training with linear kernel (hard margin, C = 1000)
- Side-by-side boundary comparison
- Noise robustness experiment: accuracy vs. σ for both models

### Run locally

```bash
git clone https://github.com/BenyaminMahdavifar/perceptron-vs-svm.git
cd perceptron-vs-svm
pip install numpy matplotlib scikit-learn jupyter
jupyter notebook Preceptron_vs_SVM.ipynb
```

---

## Repository structure

```
├── docs/
│   └── index.html          # Interactive dashboard (GitHub Pages)
├── index.html              # Root redirect → docs/
├── Preceptron_vs_SVM.ipynb # Full simulation notebook
└── README.md
```

---

## GitHub Pages setup

1. Go to **Settings → Pages**
2. Set Source to **main** branch, folder **/ (root)**
3. Save — the site is live in ~60 seconds

---

## Author

**Benyamin Mahdavifar** · [github.com/BenyaminMahdavifar](https://github.com/BenyaminMahdavifar)
