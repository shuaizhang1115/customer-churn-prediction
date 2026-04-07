# 📊 Customer Churn Prediction (End-to-End Data Science Project)

## 🚀 Project Overview
Customer churn is a critical problem in subscription-based businesses.  
This project builds a machine learning model to predict customer churn and translates model outputs into actionable business insights.  
Additionally, **SHAP analysis** is used to interpret model predictions and identify key drivers of churn.

---

## 🎯 Objectives
- Predict which customers are likely to churn  
- Focus on **recall** to minimize missed churn cases  
- Improve model performance using **threshold tuning**  
- Identify key drivers of churn for business decision-making using **SHAP interpretability**  

---

## 📂 Dataset
- Telco Customer Churn Dataset  
- ~7,000 customers, 21 features  
- Target variable: `Churn` (imbalanced ~26%)  

---

## 🔍 Approach

### 1. Data Cleaning
- Converted `TotalCharges` to numeric  
- Handled missing values  
- Standardized data types  

### 2. Feature Engineering
- AvgMonthlySpend = TotalCharges / tenure  
- Tenure grouping  
- Service-related features  

### 3. Modeling
- Logistic Regression (baseline model)  
- Random Forest (final model)  
- **XGBoost models** for advanced interpretability:
  - Model A: raw `tenure`
  - Model B: `tenure_group`
  - Model C: combined features  

### 4. Evaluation
- Confusion Matrix  
- Precision, Recall, F1 Score  
- ROC Curve & AUC  
- Threshold tuning to optimize recall  

### 5. SHAP Analysis
- SHAP **summary plots** to show overall feature importance  
- SHAP **waterfall plots** to explain high-risk individual predictions  
- Compare **raw vs grouped features** to validate feature engineering choices  

---

## 📈 Results

| Model | Recall | F1 Score | AUC |
|------|--------|----------|-----|
| Logistic Regression | ~0.52 | ~0.58 | ~0.80 |
| Random Forest | ~0.60 | ~0.63 | ~0.82 |
| Random Forest + Tuned Threshold | 🔥 Higher | 🔥 Improved | ~0.82 |
| XGBoost (Model A, raw `tenure`) | 0.62 | 0.62 | 0.838 |
| XGBoost (Model B, `tenure_group`) | 0.62 | 0.62 | 0.838 |

**Key Takeaway:** Threshold tuning improved recall, and SHAP revealed that raw `tenure` provides more granular predictive signal than grouped tenure.

---

## 🧠 Model Interpretability (SHAP)

### Summary Plots
The bar plots show the average impact of each feature on the model output.

![Model A Summary](images/shap_A.png)  
*Model A (raw `tenure`) - SHAP summary*

![Model B Summary](images/shap_B.png)  
*Model B (`tenure_group`) - SHAP summary*

### Waterfall Plots for High-Risk Customers
These plots explain why a specific customer is predicted as a high churn risk.

**Model A (raw `tenure`):**  
![Model A Waterfall](images/waterfallA.png)

**Model B (`tenure_group`):**  
![Model B Waterfall](images/waterfallB.png)

**Observation:** Raw `tenure` shows more detailed contribution patterns than grouped `tenure_group`, helping identify key drivers for individual churn risk.

---

## 🧠 Key Insights

- Month-to-month contracts → highest churn risk  
- Higher monthly charges → higher churn probability  
- Fiber optic users → elevated churn risk  
- Electronic check users → higher churn rate  
- New customers (low tenure) → high-risk segment  
- **SHAP reveals:** raw features carry more interpretive detail than grouped features  

---

## 💡 Business Recommendations

- Target high-risk customers early (especially new users)  
- Encourage long-term contracts  
- Improve fiber service quality  
- Optimize payment experience  
- Strengthen onboarding strategies  

---

## ⚠️ Challenges

- Imbalanced dataset → accuracy is misleading  
- Trade-off between recall and precision  
- Threshold selection significantly impacts performance  
- Balancing model interpretability and predictive power  

---

## 🔥 Key Takeaways

- Threshold tuning is critical in real-world ML problems  
- Recall is more important than accuracy in churn prediction  
- SHAP enables interpretable, actionable insights for high-risk customers  
- Machine learning must be combined with business understanding  

---

## 🛠️ Tech Stack

- Python (Pandas, NumPy, Scikit-learn)  
- XGBoost, Matplotlib, Seaborn  
- SHAP for model interpretability  

---

## 📌 Next Steps

- Deploy XGBoost model via Streamlit for real-time churn prediction  
- Build an automated feature engineering pipeline  
- Integrate feature store for maintainable model inputs  

---

## 👤 Author

**Shuai Zhang**  
