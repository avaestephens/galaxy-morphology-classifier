# 🌌 Galaxy Morphology Classification

> **AI 100 — Deep Learning Midterm Project**  
> Ava Stephens | Penn State University | Spring 2025

Classifying galaxy images into 10 morphological types using transfer learning (ResNet18) on the Galaxy10 DECals dataset.

---

## 📁 Repository Structure

```
galaxy-morphology-classifier/
├── galaxy_classifier.ipynb   # Main Colab-ready training notebook
├── report.pdf                # Full project report
└── README.md                 # This file
```

---

## 🗂️ Dataset

**Galaxy10 DECals** — 17,736 color galaxy images at 256×256 pixels, 10 classes.

| Class | Name |
|-------|------|
| 0 | Disturbed |
| 1 | Merging |
| 2 | Round Smooth |
| 3 | In-between Round Smooth |
| 4 | Cigar Shaped Smooth |
| 5 | Barred Spiral |
| 6 | Unbarred Tight Spiral |
| 7 | Unbarred Loose Spiral |
| 8 | Edge-on without Bulge |
| 9 | Edge-on with Bulge |

Download link (used automatically in the notebook):
```
https://astro.utoronto.ca/~hleung/shared/Galaxy10/Galaxy10_DECals.h5
```

---

## 🧠 Model

- **Architecture:** ResNet18 pretrained on ImageNet
- **Strategy:** Transfer learning — frozen backbone + custom head
- **Head:** `Dropout(0.4) → Linear(512 → 10)`
- **Framework:** PyTorch

---

## 🚀 How to Run

### Option 1: Google Colab (recommended)
1. Upload `galaxy_classifier.ipynb` to [Google Colab](https://colab.research.google.com)
2. Set Runtime → Change runtime type → **T4 GPU**
3. Run all cells top to bottom — the notebook downloads the dataset automatically

### Option 2: Local
```bash
pip install torch torchvision h5py matplotlib scikit-learn seaborn tqdm
jupyter notebook galaxy_classifier.ipynb
```

---

## 📊 Expected Results

| Metric | Value |
|--------|-------|
| Test Accuracy | ~80–85% |
| Training Time | ~12 min (Colab T4 GPU) |
| Epochs | 15 |

---

## 📄 Report

See `Galaxy_Morphology_Report.pdf` for the full writeup covering:
- Problem definition & dataset curation
- Model architecture & training methodology
- Results with confusion matrix & training curves
- Lessons learned & future directions

---

## 📚 References

- [Galaxy10 DECals](https://astronn.readthedocs.io/en/latest/galaxy10.html) — Henry Leung, University of Toronto
- He et al. (2016). *Deep Residual Learning for Image Recognition.* CVPR.
- [Galaxy Zoo](https://www.galaxyzoo.org/) — citizen science labeling project
