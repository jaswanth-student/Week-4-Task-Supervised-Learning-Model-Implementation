# Week 4 – Supervised Learning Model Implementation

## 📌 Project Overview

This project implements supervised machine learning models to predict whether an individual's annual income is greater than $50,000 using demographic, educational, occupational, and financial attributes.

The project uses the Adult Census Income dataset and follows a complete machine learning workflow, including data exploration, preprocessing, feature engineering, model training, evaluation, cross-validation, visualization, and error analysis.

Two classification algorithms were implemented and compared:

- Logistic Regression
- Random Forest Classifier

The objective is to evaluate the performance of both models and identify the most suitable approach for income classification.

---

## 🎯 Objectives

- Understand and preprocess a real-world dataset.
- Perform data cleaning and validation.
- Prepare numerical and categorical features.
- Encode the target variable for binary classification.
- Train Logistic Regression and Random Forest models.
- Evaluate models using multiple performance metrics.
- Perform cross-validation.
- Analyze feature importance.
- Visualize model performance using confusion matrices and ROC curves.
- Study misclassified records and model limitations.

---

## 📊 Dataset

The project uses the **Adult Census Income dataset**.

### Dataset Size

- Total records: **48,813**
- Total features: **15**
- Numerical features: **6**
- Categorical features: **9**

### Target Variable

The target variable is `income`.

The original income categories were normalized into two classes:

| Original Category | Cleaned Category |
|---|---|
| `<=50K` | `<=50K` |
| `<=50K.` | `<=50K` |
| `>50K` | `>50K` |
| `>50K.` | `>50K` |

Final class distribution:

- `<=50K`: **37,128 records (76.06%)**
- `>50K`: **11,685 records (23.93%)**

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the dataset using Pandas.
2. Examined the dataset shape and structure.
3. Checked data types.
4. Checked for missing values.
5. Checked for duplicate records.
6. Verified numerical feature statistics.
7. Normalized inconsistent income labels.
8. Converted the target variable into binary values:
   - `<=50K → 0`
   - `>50K → 1`
9. Separated independent variables (`X`) from the target variable (`y`).
10. Identified numerical and categorical features.
11. Applied appropriate preprocessing to numerical and categorical variables.

### Numerical Features

- age
- fnlwgt
- education-num
- capital-gain
- capital-loss
- hours-per-week

### Categorical Features

- workclass
- education
- marital-status
- occupation
- relationship
- race
- sex
- native-country

Categorical variables were encoded using One-Hot Encoding, while numerical variables were processed using StandardScaler where required.

---

## 🤖 Machine Learning Models

### 1. Logistic Regression

Logistic Regression was selected as a baseline classification model because it is simple, interpretable, computationally efficient, and well suited for binary classification.

### 2. Random Forest

Random Forest was selected as a second model because it can capture nonlinear relationships and interactions between features. It also provides feature importance values that help identify the variables contributing most to predictions.

---

## 📈 Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix
- ROC Curve
- Cross-Validation

### Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 85.32% | 73.99% | 59.65% | 66.05% | 0.906 |
| Random Forest | 85.47% | 73.30% | 61.79% | 67.05% | 0.904 |

Random Forest achieved slightly higher accuracy and F1-score, while Logistic Regression achieved a slightly higher ROC-AUC.

---

## 🔍 Cross-Validation

Five-fold cross-validation was performed to evaluate the consistency of the model.

Random Forest F1 scores across the five folds were:

```text
0.6614
0.6589
0.6657
0.6566
0.6691
