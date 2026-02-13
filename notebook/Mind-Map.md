# 1️⃣ One-Page ML Mental Map (The Whole Game)

Think of ML as **5 connected layers**.
If one layer is weak → accuracy dies.

```
Business Goal
     ↓
Problem Definition
     ↓
Data Reality Check
     ↓
Modeling Strategy
     ↓
Evaluation & Error Analysis
```

### 🧠 Layer 1: Business Goal

* What decision will be taken?
* Cost of false prediction?
* Metric that represents success?

> No metric = no model.

---

### 🧠 Layer 2: Problem Definition

* Target type?

  * Continuous → Regression
  * Discrete → Classification
  * No target → Clustering
  * Time dependent → Forecasting
* Single prediction or sequence?
* Real-time or batch?

---

### 🧠 Layer 3: Data Reality Check

* Data size (rows & features)
* Missing values
* Noise & outliers
* Leakage risk
* Class imbalance

> Bad data beats bad models every time.

---

### 🧠 Layer 4: Modeling Strategy

* Baseline first
* Simple model → complex model
* Regularization before tuning
* Cross-validation
* Feature importance

---

### 🧠 Layer 5: Evaluation & Error Analysis

* Metric vs business goal
* Overfitting check
* Segment-level errors
* Stability across folds

> A model without error analysis is unfinished.

---

# 2️⃣ ML TYPE–BASED CHECKLISTS (What to check + Statistical tests)

Now the **real value**.

---

## 🔹 A) REGRESSION MODELS (Continuous Target)

### Step-by-Step Checklist

### 1️⃣ Target Analysis

Check:

* Distribution (histogram)
* Skewness
* Outliers
* Zero / negative values

Statistical tests:

* **Shapiro-Wilk** → normality (small data)
* **Kolmogorov–Smirnov** → large data
* **Boxplot / IQR** → outliers

If skewed → consider:

* log
* Box-Cox
* Yeo-Johnson

---

### 2️⃣ Feature Analysis

Numeric features:

* Correlation with target (Pearson / Spearman)
* Multicollinearity

Tests:

* **Pearson** → linear relation
* **Spearman** → monotonic relation
* **VIF** → multicollinearity

Categorical features:

* Group mean comparison

Tests:

* **ANOVA** → category vs numeric target
* **Kruskal–Wallis** → non-normal target

---

### 3️⃣ Assumption Checks (for linear models)

* Linearity
* Homoscedasticity
* Normal residuals
* Independence

Tests:

* **Breusch–Pagan** → heteroscedasticity
* **Durbin–Watson** → autocorrelation

---

### 4️⃣ Metrics

* MAE → business-friendly
* RMSE → penalizes large errors
* R² → explanation, not accuracy

---

### 5️⃣ Error Analysis

Check:

* Residuals vs predictions
* Error by segment
* Extreme error cases

---

## 🔹 B) CLASSIFICATION MODELS (Categorical Target)

### Step-by-Step Checklist

---

### 1️⃣ Target Analysis

Check:

* Class balance
* Minority class importance

Tests:

* **Chi-square goodness-of-fit** → imbalance awareness

Rule:

* Imbalanced data ≠ accuracy metric

---

### 2️⃣ Feature vs Target

Numeric:

* Distribution per class

Tests:

* **t-test** → binary class
* **Mann–Whitney U** → non-normal
* **ANOVA** → multi-class

Categorical:

* Relationship with target

Tests:

* **Chi-square test of independence**
* **Fisher’s Exact** (small samples)

---

### 3️⃣ Encoding & Scaling

* One-hot for low cardinality
* Target / frequency encoding for high cardinality
* Scaling needed for:

  * Logistic Regression
  * SVM
  * KNN

---

### 4️⃣ Metrics (DO NOT USE ACCURACY BLINDLY)

* Precision
* Recall
* F1-score
* ROC-AUC
* PR-AUC (imbalanced)

Choose metric based on:

* False Positive cost
* False Negative cost

---

### 5️⃣ Threshold & Error Analysis

Check:

* Confusion matrix
* Wrong predictions per class
* Threshold tuning

---

## 🔹 C) CLUSTERING (No Target)

### Checklist

1. Feature scaling (mandatory)
2. Distance metric choice
3. Number of clusters

Tests / Methods:

* **Elbow method**
* **Silhouette score**
* **Davies–Bouldin index**

Validation:

* Cluster interpretability
* Business meaning

---

## 🔹 D) TIME SERIES FORECASTING

### Checklist

1. Trend
2. Seasonality
3. Stationarity

Tests:

* **ADF Test** → stationarity
* **KPSS** → trend stationarity
* **ACF / PACF** → lag selection

Rules:

* NEVER random split
* Always time-based split

---

## 🔹 E) FEATURE SELECTION (ALL TYPES)

Methods:

* Correlation filtering
* Mutual information
* Recursive Feature Elimination
* Model-based importance
