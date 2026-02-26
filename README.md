# MNIST: MLP vs. CNN

Classifying handwritten digits from MNIST with an MLP baseline (~98%) and a CNN (~99%+). Built in a single Jupyter notebook with scikit-learn and TensorFlow.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-yellowgreen)

## Overview

MNIST is 70,000 grayscale images of handwritten digits (0–9), each 28×28 pixels. This project builds two models of increasing complexity and compares their performance:

| Model | Test Accuracy | Train-Test Gap | Approach |
|-------|:------------:|:--------------:|----------|
| MLP Classifier | ~97.9% | ~0.017 | Flat 784-feature vector → dense layers (512, 256) |
| CNN | ~99.2% | ~0.005 | 2D convolutions → pooling → dense head with dropout |

The MLP treats each pixel independently. The CNN exploits spatial structure — edges, curves, and local patterns — which is why it handles the hardest digit pairs (7↔2, 4↔9, 3↔8) significantly better.

## Project Structure

```
mnist-mlp-vs-cnn/
├── MNIST_Image_Classification.ipynb   # Full analysis notebook
└── README.md
```

## Getting Started

### Requirements

- Python 3.10+
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/mnist-mlp-vs-cnn.git
cd mnist-mlp-vs-cnn
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow
```

### Run

```bash
jupyter notebook MNIST_Image_Classification.ipynb
```

The dataset is loaded automatically via `sklearn.datasets.fetch_openml` — no manual download needed.

## Notebook Sections

1. **Introduction** — Problem framing and approach
2. **Data Overview** — Shape, class distribution, sample visualization
3. **Preprocessing** — Train/test split, normalization, CNN reshape
4. **MLP Classifier** — Baseline training, evaluation, 5-fold cross-validation
5. **CNN** — Architecture, training curves, evaluation
6. **Results & Comparison** — Side-by-side accuracy table and takeaways

## Key Takeaways

- Spatial structure matters — even on a "simple" dataset like MNIST, 2D convolutions yield a meaningful accuracy gain over flat vectors.
- The MLP's errors are predictable: structurally similar digits that need local feature detection to tell apart.
- Both models generalize well with minimal overfitting, confirmed by cross-validation (MLP) and train/val curves (CNN).

## Author

**Mickias Ambaye** — February 2026
