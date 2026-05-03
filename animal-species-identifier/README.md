# 🦁 Animal Species Identifier

A machine learning model to identify and classify animal species using a Random Forest Classifier with hyperparameter tuning via GridSearchCV.

## 📋 Overview

This project trains a **Random Forest Classifier** on animal feature data to predict species classification. It uses **GridSearchCV** for automated hyperparameter optimization to maximize model accuracy.

## 🧠 Model

- **Algorithm:** Random Forest Classifier
- **Tuning:** GridSearchCV with 5-fold cross-validation
- **Scaling:** StandardScaler normalization

## 📁 File Structure

```
animal-species-identifier/
│
├── animal_species_identifier.ipynb    # Main notebook
├── requirements.txt
└── README.md
```

## 🗂️ Dataset

The notebook loads data from a CSV file. You need to supply your own animal species dataset.

**Recommended datasets:**
- [Zoo Animal Classification — Kaggle](https://www.kaggle.com/datasets/uciml/zoo-animal-classification)
- [Animal Features Dataset — UCI ML Repository](https://archive.ics.uci.edu/dataset/111/zoo)

After downloading, update the file path in Cell 2:
```python
df = pd.read_csv("zoo.csv")  # <-- update to your actual path
```

Also update the target column name in Cell 3:
```python
TARGET_COLUMN = 'class_type'  # <-- update to your actual target column
```

## ⚙️ Setup & Installation

```bash
pip install -r requirements.txt
jupyter notebook animal_species_identifier.ipynb
```

## 📦 Requirements

```
pandas
scikit-learn >= 1.1
numpy
matplotlib
```

## 🔧 Hyperparameter Grid

```python
param_grid = {
    'n_estimators': [100, 200, 300],
    'max_features': ['sqrt', 'log2'],
    'max_depth': [None, 10, 20, 30],
    'min_samples_split': [2, 5, 10],
    'min_samples_leaf': [1, 2, 4]
}
```

## 📊 Evaluation Metrics

- Accuracy Score
- Classification Report (Precision, Recall, F1 per class)
- Feature Importance Plot

