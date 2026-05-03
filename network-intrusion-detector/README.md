# 🛡️ Network Intrusion Detector

A machine learning system to detect network intrusions and anomalies in network traffic data, using both classical ML classifiers and deep learning approaches.

## 📋 Overview

This project builds a binary classifier that labels network connections as **normal** or **anomaly** (intrusion). It explores multiple model architectures to find the best-performing approach.

## 🧠 Models Implemented

| Model | Type |
|-------|------|
| Random Forest | Ensemble |
| Support Vector Machine (SVM) | Kernel-based |
| K-Nearest Neighbors (KNN) | Instance-based |
| Linear Discriminant Analysis (LDA) | Linear |
| Quadratic Discriminant Analysis (QDA) | Quadratic |
| LSTM Neural Network | Deep Learning |
| Sequential Dense Network | Deep Learning |

## 📁 File Structure

```
network-intrusion-detector/
│
├── network_intrusion_detector.ipynb   # Main notebook
├── requirements.txt
└── README.md
```

## 🗂️ Dataset

This notebook is designed to work with the **NSL-KDD** or **KDD Cup 1999** dataset.

Download from: https://www.unb.ca/cic/datasets/nsl.html

Expected files:
- `Train_data.csv` — Training data with `class` column (`normal` / `anomaly`)
- `Test_data.csv` — Test data

Update the file paths in the notebook after downloading.

## ⚙️ Setup & Installation

```bash
# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook network_intrusion_detector.ipynb
```

## 📦 Requirements

```
pandas
numpy
scikit-learn
tensorflow
keras
matplotlib
seaborn
scipy
```

## 📊 Evaluation Metrics

- Accuracy Score
- Precision, Recall, F1-Score
- ROC-AUC Score
- Classification Report

## 🔧 Key Steps

1. **Load Data** — Read CSV train/test files
2. **EDA** — Histograms for numeric features, bar charts for categorical
3. **Preprocessing** — Drop zero-variance columns, handle missing values, one-hot encode categoricals
4. **Feature Scaling** — StandardScaler normalization
5. **Model Training** — Train multiple classifiers
6. **Evaluation** — Compare models using accuracy, F1, ROC-AUC

## ⚠️ Known Issues / TODO

- [ ] Fix hardcoded local file paths → use relative paths or CLI args
- [ ] `accuracy_score` was imported but called on regression output in earlier cells — switch to `RandomForestClassifier` for binary classification
- [ ] `regression_report` does not exist in sklearn — replace with `classification_report`
- [ ] Add model persistence with `pickle` / `joblib`
- [ ] Add confusion matrix visualization
