# 📈 Hybrid Sales Forecasting (ETS vs Prophet)

A professional time series forecasting project that applies a **hybrid forecasting strategy** by combining classical statistical models (ETS) with modern machine learning forecasting (Prophet), optimized using rolling cross-validation and hyperparameter tuning.

---

## 🚀 Project Overview

Sales forecasting is critical for business planning, inventory optimization, and decision-making.  
However, different product categories often show different demand behaviors:

- Some categories are stable and predictable  
- Others are volatile due to promotions, trend shifts, or seasonal spikes  

To address this, this project implements a **Hybrid Forecasting Framework**, selecting the best forecasting model per category.

---

## ✅ Key Features

- Group-level forecasting by **Category** (can be extended to Region)
- Monthly time series aggregation from transactional retail data
- **ETS (Holt-Winters)** baseline forecasting
- **Prophet forecasting** with:
  - Holiday effects
  - Log transformation
  - Hyperparameter tuning
  - Rolling Cross-Validation (more reliable evaluation)
- Hybrid strategy: choose ETS or Prophet per group based on lowest RMSE
- Automated report outputs (CSV + charts)

---

## 🧠 Models Implemented

### 1. ETS Baseline (Holt-Winters)
Used as a strong benchmark model, especially effective for stable demand patterns.

### 2. Prophet Forecasting (Tuned + CV)
Prophet is applied for categories with higher volatility and nonlinear demand trends.

Prophet is enhanced with:

- Changepoint flexibility
- Seasonality tuning
- Holiday impact modeling
- Rolling cross-validation evaluation

---

## 📊 Model Selection Results

The best model was chosen per category based on RMSE performance:

| Category          | ETS RMSE | Prophet CV RMSE | Selected Model |
|------------------|----------|----------------|----------------|
| Furniture        | 5047.93  | 4588.89        | Prophet ✅     |
| Office Supplies  | 7611.67  | 8820.22        | ETS ✅         |
| Technology       | 10098.34 | 8197.56        | Prophet ✅     |

Model selection count:

- Prophet selected: **2 categories**
- ETS selected: **1 category**

---

## 🔍 Best Prophet Parameters (Per Category)

| Category          | changepoint_prior_scale | seasonality_prior_scale | holidays_prior_scale | mode      |
|------------------|--------------------------|--------------------------|----------------------|----------|
| Furniture        | 0.1                      | 5                        | 1                    | additive |
| Office Supplies  | 0.1                      | 1                        | 5                    | additive |
| Technology       | 0.1                      | 10                       | 10                   | additive |

---

## 📂 Outputs Generated

All results are exported automatically into:

