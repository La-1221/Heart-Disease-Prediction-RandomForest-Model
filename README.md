# Predicting Heart Disease with a Random Forest Classifier

## Debre Tabor University

**Gafat Institute of Technology**\
**Department of Computer Science**\
**Course: Data Mining**

### Group Members

Name ID

---

Yordanos Enawgaw 1493
Amanuel Bewket 1451
Lakachew Ferede 1284
Mekedes Kibebew 0962
Heaven Mandefro 1610
Selome Zenebe 1297

**Submitted to:** Mr. Moges\
**Submission Date:** 10/03/2018 E.C.

---

## Table of Contents

1.  [Declaration](#declaration)\
2.  [Introduction](#introduction)\
3.  [Methodology](#methodology)\
4.  [Results](#results)\
5.  [Discussion](#discussion)\
6.  [Conclusion](#conclusion)

---

## Declaration

We hereby declare that this report titled **"Predicting Heart Disease
with a Random Forest Classifier"** is our original work, conducted under
the guidance of our instructor. All external sources used in this
project have been properly acknowledged.

---

## Introduction

This project focuses on predicting the likelihood of heart disease using
machine learning techniques applied to the **Heart Disease UCI dataset**
(Kaggle dataset ID: _ronitf/heart-disease-uci_).\
The goal is to develop a reliable and interpretable model that can
support early medical diagnosis.

The complete workflow was implemented in Google Colab and includes:

- Data acquisition through the Kaggle API\
- Preprocessing and feature engineering\
- Exploratory Data Analysis (EDA)\
- Model training and evaluation\
- Comparative performance analysis\
- Model interpretation

Several algorithms were tested (Logistic Regression, SVM, Decision Tree,
KNN, Gradient Boosting, XGBoost), but the **Random Forest Classifier**
achieved the best performance and was selected as the final model.

---

## Methodology

### 1. Data Preparation

- Missing values were imputed using median values for numerical
  features.\
- Categorical features were encoded appropriately.\
- New engineered features were introduced:
  - `age_group` → _young_, _middle-aged_, _old_
  - `chol_level` → _normal_, _borderline_, _high_

These helped improve interpretability and model accuracy.

---

### 2. Exploratory Data Analysis (EDA)

Key findings: - Older age groups showed a higher probability of heart
disease.\

- High cholesterol levels also strongly correlated with disease
  presence.\
- A correlation heatmap helped identify feature relationships.\
- Pair plots revealed non-linear interactions between variables.

---

### 3. Model Building & Evaluation

The dataset was split into **80% training** and **20% validation** using
stratified sampling.

Models were evaluated using: - **Accuracy** - **AUC (Area Under
Curve)** - **Precision** - **Recall** - **F1-Score** - **Confusion
Matrix**

The **Random Forest Classifier** delivered the best and most balanced
results across all metrics.

---

### Why Random Forest?

- Captures complex non-linear patterns.
- Reduces overfitting through ensemble averaging.
- Robust to noise, outliers, and missing data.
- Requires minimal parameter tuning.
- Parallelizable and efficient even on limited hardware.
- Suitable for medical applications requiring balanced precision and
  recall.

---

## Results

### Model Comparison

Model Accuracy AUC

---

**Random Forest** **0.8525** **0.8500**
XGBoost 0.8361 0.8333
Gradient Boosting 0.8197 0.8167
Logistic Regression 0.8033 0.8000
SVM 0.7869 0.7833
Decision Tree 0.7705 0.7667
KNN 0.7541 0.7500

### Best Model: Random Forest

- **Validation Accuracy:** 85.25%\
- **AUC:** 0.8500\
- **Precision:** 0.8571\
- **Recall:** 0.8571\
- **F1-Score:** 0.8571

### Confusion Matrix

                          Predicted No Disease   Predicted Disease

---

**Actual No Disease** 20 3
**Actual Disease** 3 20

---

## Discussion

### Reasons for Random Forest Superiority

- **Ensemble Learning:** Reduces overfitting and improves
  reliability.\
- **Handles Non-Linear Patterns:** Helpful for complex medical
  datasets.\
- **Robustness:** Works well with noise, outliers, and missing
  values.\
- **Parallel Training:** Efficient on Google Colab/on modest
  hardware.\
- **Better Generalization:** Compared to single decision trees.

### Comparison with Other Models

- **Decision Tree:** Overfits easily.\
- **Logistic Regression:** Highly interpretable but linear.\
- **SVM / KNN:** Sensitive to scaling and parameter tuning.\
- **XGBoost / Gradient Boosting:** Good performance but more
  computationally expensive.

### Limitations

- Limited interpretability → mitigated using SHAP or LIME.\
- Dataset size is relatively small → larger datasets improve
  robustness.

### Medical Relevance

The model aligns with widely known clinical patterns (age, cholesterol,
exercise-induced angina), reinforcing its reliability.

---

## Conclusion

The Random Forest Classifier proved to be the most effective model,
delivering **85.25% accuracy** with well-balanced precision and recall.
Its ensemble nature enables it to capture complex relationships within
the dataset, outperforming all other tested algorithms.

### Future Work

- Hyperparameter optimization (`n_estimators`, `max_depth`, etc.)\
- Expanding the dataset with multi-source medical records\
- Integrating explainability tools to improve clinical acceptance

This project demonstrates the real-world potential of machine learning
in early heart disease detection and medical decision support.
