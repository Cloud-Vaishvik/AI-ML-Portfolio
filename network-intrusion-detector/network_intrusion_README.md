# 🛡️ Network Intrusion Detector

A machine learning system to detect network intrusions and anomalies in network traffic data, using both classical ML classifiers and deep learning (Dense + LSTM networks).

## 📋 Overview

This project builds a **binary classifier** that labels network connections as **normal** or **anomaly** (intrusion). It trains and compares multiple model architectures to find the best-performing approach, then evaluates using accuracy, F1 score, classification report, and ROC-AUC curve.

## 🧠 Models Implemented

| Model | Type |
|-------|------|
| Random Forest Classifier | Ensemble |
| Support Vector Machine (SVM) | Kernel-based |
| K-Nearest Neighbors (KNN) | Instance-based |
| Linear Discriminant Analysis (LDA) | Linear |
| Quadratic Discriminant Analysis (QDA) | Quadratic |
| Sequential Dense Neural Network | Deep Learning |
| LSTM Neural Network | Deep Learning |

## 📁 File Structure

```
network-intrusion-detector/
│
├── network_intrusion_detector.ipynb   # Main notebook
├── requirements.txt
└── README.md
```

## 🗂️ Dataset

This notebook is designed to work with the **NSL-KDD** dataset.

**Download from:** https://www.unb.ca/cic/datasets/nsl.html

Expected files (place in the same folder as the notebook):
- `Train_data.csv` — Training data with `class` column (`normal` / `anomaly`)
- `Test_data.csv` — Test data

Update the file paths in Cell 3 if your files are in a different location:
```python
df_train = pd.read_csv('Train_data.csv')   # <-- update if needed
df_test  = pd.read_csv('Test_data.csv')    # <-- update if needed
```

## ⚙️ Setup & Installation

```bash
pip install -r requirements.txt
jupyter notebook network_intrusion_detector.ipynb
```

## 📦 Requirements

```
pandas
numpy
scikit-learn >= 1.1
tensorflow >= 2.15
keras
matplotlib
seaborn
scipy
```

## 🔧 Notebook Structure

| Cell | Description |
|------|-------------|
| 1 | Install packages |
| 2 | All imports (sklearn, tensorflow, keras) |
| 3 | Load train & test datasets |
| 4 | EDA — distributions, zero-variance column removal |
| 5 | Categorical feature plots + class distribution |
| 6 | Preprocessing — encode, split, scale |
| 7 | Train & compare 5 classical classifiers |
| 8 | Classification report + ROC curve for best model |
| 9 | Deep Learning — Sequential Dense Network |
| 10 | Deep Learning — LSTM Network |
| 11 | Save best model to `.pkl` and `.keras` |

## 📊 Evaluation Metrics

- Accuracy Score
- F1 Score (weighted)
- Classification Report (Precision, Recall, F1 per class)
- ROC-AUC Curve

## ✅ Bug Fixes Applied

| # | Cell | Issue | Fix |
|---|------|-------|-----|
| 1 | 2 | `RandomForestRegressor` used for classification | Replaced with `RandomForestClassifier` |
| 2 | 2 | Standalone `keras` imports conflict with TensorFlow | Changed all to `tensorflow.keras` |
| 3 | 2 | `regression_report` does not exist in sklearn | Replaced with `classification_report` |
| 4 | 2 | `accuracy_score` imported but used on regressor output | Now correctly used with classifier predictions |
| 5 | 3 | Extra quotes inside CSV path string caused file not found | Removed extra `"` from path strings |
| 6 | 3 | Hardcoded local `C://Users/asus/` paths | Changed to relative paths |
| 7 | 3 | `venv` activation inside notebook has no effect | Removed misleading shell commands |
| 8 | 6 | `fit_transform` applied to test set (data leakage) | Changed test set to `transform` only |
| 9 | 6 | `'Date and Time'` dropped twice after already being dropped | Removed duplicate drop; corrected target to `class` column |
| 10 | 6 | `stratify=y` used before `y` was label-encoded | Moved encoding before the split |
| 11 | 10 | LSTM requires 3D input — no reshape was done | Added `.reshape(samples, 1, features)` for LSTM cells |
| 12 | — | Empty cells at end with no content | Replaced with model saving cell using `pickle` |
