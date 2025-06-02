
# 📊 Predicting Customer Churn in Telecommunication Industry

## 🧠 Executive Summary
This project addresses the critical challenge of customer churn in the highly competitive telecommunications sector. By leveraging a data-driven machine learning approach, we aim to help businesses identify at-risk customers early, reduce churn, and ultimately improve customer retention strategies—minimizing losses and maximizing customer lifetime value.

## 🏢 Business Background
The telecom industry experiences annual churn rates between 10–25%, with customer acquisition being 5–10× more expensive than retention. With low switching costs and similar service offerings, customer loyalty is fragile. Reducing churn, especially among high-value or long-tenured customers, is crucial for sustaining profitability.

## 🎯 Business Objective
- Predict customer churn using a machine learning model
- Focus on cost-saving by reducing false negatives (missed churns)
- Provide actionable business strategies to improve retention

## 📦 Business Strategy Recommendation
### 1. 📦 Bundling Packages
- **Stream Saver Bundle**: Internet 30 Mbps + Streaming TV/Movies @ IDR 320,000/month
- **Family Shield Bundle**: Internet 50 Mbps + TV + Phone + Device Protection @ IDR 465,000/month
- **Add-ons**: OnlineSecurity, Premium Streaming, Mobile Data add-ons

### 2. 💳 Payment Optimization
- Offer discounts for switching to 1-year/2-year contracts
- “Lock-and-Save” program for long-term subscriptions

### 3. 💙 Retention & Loyalty Programs
- Identify high-spending customers (>IDR 500,000/month) for targeted retention
- Provide loyalty perks for long-tenured users

## 📊 Dataset Information
- **Total Rows**: 7032
- **Columns**: 21 features including demographics, service usage, and billing
- **Period**: Q3 2018 (Jul–Sep)
- **Location**: California, USA

### Key Data Insights:
- High churn among: new customers, fiber optic users, and users without security/tech support
- Low churn among: users with 2-year contracts or tenure > 50 months
- MonthlyCharges ↑ + Tenure ↓ = High Churn Risk

## 🧩 Data Processing
- **Feature Engineering**: Selected features include contract type, tenure, monthly charges, etc.
- **Preprocessing**: One-hot encoding, robust scaling
- **Train-Test Split**: 80/20 with `stratify=y` and `random_state=9`

## 🤖 Machine Learning Model
- **Model Used**: Logistic Regression (interpretable & cost-effective)
- **Model Tuning**: Hyperparameter optimization with cross-validation (emphasizing F2-score)
- **Key Metric**: F2-score = 0.63 (post-tuning), improved from 0.57

### 🎯 Why Logistic Regression?
- Best trade-off between interpretability, performance, and cost reduction
- Focus on minimizing False Negatives (missed churns), which are most costly

## 💰 Cost Impact Analysis
| Scenario             | False Positives (FP) | False Negatives (FN) | Total Cost (USD) |
|----------------------|----------------------|-----------------------|------------------|
| Before Tuning        | 111 × $150 = 16,650  | 175 × $240 = 42,000   | **$58,650**      |
| After Tuning         | 160 × $150 = 24,000  | 137 × $240 = 32,880   | **$56,880**      |
| 💡 **Savings**       |                      |                       | **$1,770 (↓1.53%)** |

## 📈 Model Evaluation
- Reduced FN by 38 cases (from 175 to 137)
- F2-score improved, focusing on recall
- Stable performance across cross-validation folds

## 🔍 Key Features (by importance)
- Tenure (↑ loyalty → ↓ churn)
- Contract Type (longer contracts → ↓ churn)
- TotalCharges (↑ spending sometimes → ↑ dissatisfaction)
- InternetService = FiberOptic (↑ churn risk)

## 🚧 Limitations
- No time-series behavior or subscription timestamps
- Missing data initially in `TotalCharges`
- Limited behavioral features like complaints, satisfaction, or usage logs

## 🔧 Deployment Plan
- Deploy Logistic Regression model in production
- Schedule regular evaluation & retraining
- Automate churn pipeline with workflow tools (e.g., N8N)

## 🚀 Conclusion
Our model successfully predicts customer churn with strong interpretability and significant cost reduction potential. By adopting the proposed business strategies and leveraging machine learning, telecom companies can proactively retain customers and improve profitability.

---

📎 **Author**: Shafy Hafidz  
📅 **Date**: May 2025  
🏢 **Capstone Project – JCDS**
