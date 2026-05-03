# 🦁 Animal Species Identifier

A machine learning model to identify and classify animal species using a Random Forest algorithm with hyperparameter tuning.

## 📋 Overview

This project trains a **Random Forest** model on animal feature data to predict species classification. It uses **GridSearchCV** for automated hyperparameter optimization to maximize model performance.

## 🧠 Model

- **Algorithm:** Random Forest (Regressor / Classifier)
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

After loading, update the `target_column` placeholder with your actual label column name (e.g., `'class_type'`, `'species'`).

## ⚙️ Setup & Installation

```bash
pip install -r requirements.txt
jupyter notebook animal_species_identifier.ipynb
```

## 📦 Requirements

```
pandas
scikit-learn
numpy
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

- Mean Squared Error (MSE)
- R² Score
- Accuracy Score

## ⚠️ Known Issues / TODO

- [ ] Replace placeholder `'target_column'` with actual target column name
- [ ] Switch from `RandomForestRegressor` to `RandomForestClassifier` for species classification (categorical target)
- [ ] Use `classification_report` instead of MSE/R² for categorical targets
- [ ] Add feature importance visualization
- [ ] Add confusion matrix
- [ ] Fix cascading `NameError` caused by earlier cell failure — run cells in order after fixing target column
