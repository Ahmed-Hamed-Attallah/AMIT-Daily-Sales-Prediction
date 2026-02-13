# 📈 End-to-End Sales Forecasting & Business Insights Project

## 📌 Overview
This project builds a complete **data-driven forecasting system** designed to:

- Analyze historical sales data
- Extract behavioral patterns
- Detect trends & seasonality
- Segment business dynamics
- Predict future sales

The workflow moves from raw transactional data to a production-ready forecasting model using statistical diagnostics, clustering, and machine learning.

---

## 🎯 Objectives

The project aims to answer:

- What drives sales performance?
- How do customer behavior & logistics impact revenue?
- Is there seasonality in sales?
- Can we segment business patterns?
- Can we predict future sales accurately?

---

## 🧱 Project Pipeline

### Phase 1 — Data Cleaning & Feature Engineering
- Removed inconsistent records (Order Date > Ship Date)
- Created time-based features:
  - Year
  - Month
  - Day of week
  - Weekend indicator
  - Quarter

---

### Phase 2 — Exploratory Data Analysis (EDA)

#### Univariate Analysis
- Sales distribution
- Shipping duration distribution
- Outliers detection

#### Categorical Analysis
- Sales by:
  - Category
  - Segment
  - Ship Mode
  - Region
  - State
  - Product

#### Time-Based Analysis
- Sales over time
- Monthly trend
- Weekly trend
- Quarterly trend
- Weekend vs Weekday performance

---

### Phase 3 — Statistical Diagnostics

- Skewness check
- Outlier detection
- Correlation Analysis:
  - Pearson
  - Spearman
- Multicollinearity check (VIF)

---

### Phase 4 — Behavioral Structuring

#### Clustering
Used **KMeans** to identify business operational patterns.

Clustering based on:
- Sales behavior
- Order volume
- Customer activity
- Product diversity

Evaluation metrics:
- Silhouette Score
- Calinski-Harabasz Index
- Davies-Bouldin Score

---

### Phase 5 — Forecasting Model

#### Models Tested
- Ridge
- Lasso
- Random Forest
- Gradient Boosting
- Extra Trees
- AdaBoost

Used:
- TimeSeriesSplit
- Feature Selection
- Scaling comparison

---

### 🏆 Best Model
After tuning, the best performing model was:

👉 **Gradient Boosting Regressor**

Optimized using:
- GridSearchCV
- Multi-metric scoring:
  - RMSE
  - MAE

---

## 📊 Model Evaluation

Target was log-transformed for stability.

Evaluation metrics:

- RMSE
- MAE
- R² Score

Predictions were inverse-transformed to real sales values.

---

## 🧠 Key Capabilities

✔ Detects sales patterns  
✔ Captures seasonality  
✔ Identifies business clusters  
✔ Forecasts revenue trends  
✔ Supports strategic decision-making  

---

## 🛠 Tech Stack

- Python
- Pandas
- Scikit-learn
- Statsmodels
- Plotly
- Seaborn
- Numpy

---

## 🚀 Future Improvements

- Deploy as API
- Add real-time forecasting
- Integrate external signals (marketing / holidays)
- Move to advanced models (XGBoost / LSTM)

---

## 📂 Output

- Sales Forecasting Model
