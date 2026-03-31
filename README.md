# 📊 Customer Churn Prediction (End-to-End Data Science Project)

## 🚀 Project Overview
Customer churn is a critical problem in subscription-based businesses.  
This project builds a machine learning model to predict customer churn and translates model outputs into actionable business insights.

---

## 🎯 Objectives
- Predict which customers are likely to churn  
- Focus on **recall** to minimize missed churn cases  
- Improve model performance using **threshold tuning**  
- Identify key drivers of churn for business decision-making  

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

### 4. Evaluation
- Confusion Matrix  
- Precision, Recall, F1 Score  
- ROC Curve & AUC  

### 5. Threshold Tuning 🔥
- Optimized classification threshold instead of using default 0.5  
- Improved recall significantly for churn class  

---

## 📈 Results

| Model | Recall | F1 Score | AUC |
|------|--------|----------|-----|
| Logistic Regression | ~0.52 | ~0.58 | ~0.80 |
| Random Forest | ~0.60 | ~0.63 | ~0.82 |
| Random Forest + Tuned Threshold | 🔥 Higher | 🔥 Improved | ~0.82 |

### Key Takeaway
The tuned model achieved better recall, which is critical because missing churn customers leads to lost revenue.

---

## 🧠 Why Recall Matters

In churn prediction, failing to identify a true churn customer is more costly than incorrectly flagging a customer as high-risk.  
Therefore, recall was prioritized over accuracy during model evaluation and optimization.

---

## 🧠 Key Insights

- Month-to-month contracts → highest churn risk  
- Higher monthly charges → higher churn probability  
- Fiber optic users → elevated churn risk  
- Electronic check users → higher churn rate  
- New customers (low tenure) → high-risk segment  

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

---

## 🔥 Key Takeaways

- Threshold tuning is critical in real-world ML problems  
- Recall is more important than accuracy in churn prediction  
- Machine learning must be combined with business understanding  

---

## 🛠️ Tech Stack

- Python (Pandas, NumPy)  
- Scikit-learn  
- Matplotlib / Seaborn  

---

## 📌 Next Steps

- XGBoost / LightGBM  
- Cross-validation  
- Model deployment (Streamlit)  

---

## 👤 Author

**Shuai Zhang**  
