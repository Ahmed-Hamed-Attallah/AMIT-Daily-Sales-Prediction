# MASTER DECISION GUIDE

## (What to use, when to use it, and what error it fixes)

---

# 1️⃣ TARGET VARIABLE — WHAT TO DO & WHEN

## 🔹 Regression Target

### 🔸 Problem: Target is **skewed**

**Use when**

* Histogram is long-tailed
* RMSE >> MAE

**Do**

* `log(y + 1)`
* Yeo-Johnson (if zeros / negatives exist)

**Fixes**

* Large error domination
* Poor convergence
* Over-penalization of outliers

---

### 🔸 Problem: Extreme outliers

**Use when**

* Boxplot shows long whiskers
* Business says values are “rare but real”

**Do NOT**

* Blindly delete

**Do**

* Winsorization
* Robust models (Huber, Quantile Regression)
* Use MAE instead of RMSE

---

## 🔹 Classification Target

### 🔸 Problem: Class imbalance

**Use when**

* Minority < 20%
* Accuracy looks high but recall is bad

**Do**

* Change metric (F1 / Recall / PR-AUC)
* Class weights
* SMOTE (only on train set)

**Do NOT**

* Oversample test set

---

# 2️⃣ FEATURE TYPE — WHAT TO USE & WHEN

---

## 🔹 Numeric Features

### 🔸 Problem: Non-linear relationship with target

**Use when**

* Scatter plot is curved
* Pearson ≈ 0 but model still improves

**Do**

* Tree-based models
* Polynomial features
* Log / sqrt transforms

**Avoid**

* Linear regression without transformation

---

### 🔸 Problem: Strong multicollinearity

**Use when**

* VIF > 5
* Correlation > 0.85

**Do**

* Drop one feature
* Ridge / ElasticNet
* PCA (only if interpretability not needed)

**Avoid**

* Lasso alone (unstable selection)

---

## 🔹 Categorical Features

### 🔸 Problem: Low cardinality (≤10)

**Use**

* One-hot encoding

**Avoid**

* Label encoding (adds fake order)

---

### 🔸 Problem: High cardinality (>20)

**Use when**

* Many unique values (city, product)

**Do**

* Target encoding
* Frequency encoding
* Group rare categories

**Avoid**

* One-hot → dimensional explosion

---

# 3️⃣ STATISTICAL TESTS — WHEN TO USE WHICH

---

## 🔹 Normality Tests

| Situation         | Use          |
| ----------------- | ------------ |
| Small data (<500) | Shapiro-Wilk |
| Large data        | KS test      |
| Visual check      | Q-Q plot     |

⚠️ Rule:
Normality matters **only** for:

* Linear regression assumptions
* Parametric tests

---

## 🔹 Numeric vs Numeric

| Relationship | Use                |
| ------------ | ------------------ |
| Linear       | Pearson            |
| Monotonic    | Spearman           |
| Non-linear   | Mutual Information |

---

## 🔹 Categorical vs Numeric

| Data condition | Test                  |
| -------------- | --------------------- |
| Normal target  | ANOVA                 |
| Non-normal     | Kruskal–Wallis        |
| Binary target  | t-test / Mann–Whitney |

---

## 🔹 Categorical vs Categorical

| Condition    | Test         |
| ------------ | ------------ |
| Large sample | Chi-square   |
| Small counts | Fisher Exact |

---

# 4️⃣ MODEL SELECTION — WHEN TO USE WHAT

---

## 🔹 Linear Models

**Use when**

* Interpretability matters
* Relationship roughly linear
* Low data size

**Avoid when**

* Strong interactions
* Non-linearity

---

## 🔹 Tree-Based Models

**Use when**

* Non-linear data
* Mixed feature types
* Feature interactions exist

**Watch for**

* Overfitting → limit depth, min_samples

---

## 🔹 Boosting Models

**Use when**

* Tabular data
* Medium–large dataset
* You want performance over interpretability

**Avoid**

* Dirty data
* Severe leakage

---

# 5️⃣ SCALING — WHEN NEEDED, WHEN NOT

| Model             | Scaling |
| ----------------- | ------- |
| Linear / Logistic | YES     |
| SVM / KNN         | YES     |
| Tree-based        | NO      |
| Neural Networks   | YES     |

---

# 6️⃣ TRAIN–TEST SPLIT — CRITICAL DECISIONS

---

## 🔹 Time dependency exists?

**Use**

* Time-based split

**Never**

* Random split

---

## 🔹 Small dataset?

**Use**

* Cross-validation (5–10 folds)

---

# 7️⃣ OVERFITTING — HOW TO DETECT & FIX

### Detect

* Train >> Test metric
* CV variance high

### Fix

* Reduce model complexity
* Regularization
* More data
* Feature pruning

---

# 8️⃣ ERROR ANALYSIS — WHEN & HOW

### When to do

* Always after first model

### How

* Plot residuals
* Analyze worst 5% errors
* Segment errors by feature

**If error is systematic → feature problem**
**If error is random → model limit**

---

# 9️⃣ FINAL DECISION RULE (MEMORIZE THIS)

> **Data problem → Feature fix → Model choice → Metric alignment**

Never reverse this order.

---
