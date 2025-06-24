# 🚗 Car Evaluation Classification using Supervised Learning

This project applies a variety of classification models to predict the overall evaluation of cars based on attributes such as price, maintenance cost, capacity, and safety. The project explores the impact of feature encoding techniques and evaluates model performance using **Cohen’s Kappa score**, with special attention to **class imbalance** in the dataset.

This work was completed as part of the **Predictive Analytics** course at the **Carlson School of Management**, University of Minnesota.

---

## 📦 Dataset

- **Source**: UCI Machine Learning Repository  
- **Name**: Car Evaluation Data Set  
- **Records**: 1,728 samples  
- **Features**: 6 categorical features (buying price, maintenance, doors, persons, luggage boot size, safety)  
- **Target**: Car Evaluation (`unacc`, `acc`, `good`, `vgood`)  
- [🔗 Dataset Link](https://archive.ics.uci.edu/ml/datasets/Car+Evaluation)

---

## 🎯 Objective

- Predict the categorical evaluation of cars using supervised learning techniques.
- Compare model performance across:
  - **Decision Tree**
  - **K-Nearest Neighbors (KNN)**
  - **Logistic Regression**
  - **Naïve Bayes**
  - **Support Vector Machine (SVM)**
- Investigate the effect of treating ordinal input variables as:
  - **Categorical** (via One-Hot Encoding)
  - **Numeric** (via Ordinal Encoding)

---

## 🧠 Methodology

- Two encoding strategies tested:
  - **One-Hot Encoding** (treats features as categorical)
  - **Ordinal Encoding** (treats features as ranked numeric)
- **Nested Cross-Validation** used for:
  - Hyperparameter tuning (inner loop)
  - Performance estimation (outer loop)
- Due to significant **class imbalance**, **Cohen’s Kappa** was selected as the primary evaluation metric.

---

## 🧪 Model Performance (Cohen’s Kappa Score)

### One-Hot Encoding Results:
| Model              | Kappa Score (± SD) |
|--------------------|--------------------|
| **SVM**            | **0.9987 ± 0.0025** |
| Decision Tree      | 0.9175 ± 0.0139     |
| Logistic Regression| 0.8519 ± 0.0082     |
| KNN                | 0.6705 ± 0.0678     |
| Naïve Bayes        | 0.6321 ± 0.0275     |

### Ordinal Encoding Results:
| Model              | Kappa Score (± SD) |
|--------------------|--------------------|
| SVM                | 0.9735 ± 0.0073     |
| Decision Tree      | 0.9300 ± 0.0365     |
| KNN                | 0.7395 ± 0.0432     |
| Naïve Bayes        | 0.2755 ± 0.0241     |
| Logistic Regression| 0.1609 ± 0.0477     |

---

## 🏆 Best Model

- **SVM with One-Hot Encoding** achieved near-perfect classification:
  - **Kappa = 0.9987 ± 0.0025**
  - **100% precision, recall, and F1-score** for all classes (`unacc`, `acc`, `good`, `vgood`)
  - Demonstrated robustness despite significant class imbalance
- One-hot encoding significantly outperformed ordinal encoding, especially for models sensitive to feature scaling and linearity (SVM, Logistic Regression).
