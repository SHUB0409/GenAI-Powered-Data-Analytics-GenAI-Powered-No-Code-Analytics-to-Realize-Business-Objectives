# GenAI-Powered-Data-Analytics-GenAI-Powered-No-Code-Analytics-to-Realize-Business-Objectives
Exploratory data analysis and risk profiling---In this task, you will conduct an EDA on Geldium’s dataset to help Tata iQ’s analytics team and Geldium’s decision-makers understand the current state of their data. Your analysis will shape how the company refines its delinquency risk model and improves its intervention strategies..

# 💳 Credit Delinquency Prediction Project (Geldium x Tata iQ)

## 🧩 Project Overview
This project focuses on analyzing customer credit and payment behavior to identify key indicators of **delinquency risk**.  
Conducted as part of the **Tata iQ - Geldium Predictive Modeling Challenge**, the goal was to perform an in-depth **Exploratory Data Analysis (EDA)** and prepare the dataset for building a predictive model that can forecast which customers are most likely to become delinquent.

---

## 📁 Project Deliverables
| File Name | Description |
|------------|-------------|
| `Delinquency_prediction_dataset.xlsx` | Original dataset containing 500+ customer financial and behavioral records. |
| `Full_EDA_Report_All_Steps.pdf` | Comprehensive EDA report including data structure, cleaning, missing value handling, and early risk detection. |

---

## 🧠 Project Workflow

### **Step 1: Data Structure and Quality Review**
- Dataset contained ~500 records and 19 columns (mix of numeric and categorical features).  
- **Target Variable:** `Delinquent_Account` (binary 0 = not delinquent, 1 = delinquent).  
- Key columns included:  
  `Credit_Score`, `Credit_Utilization`, `Debt_to_Income_Ratio`, `Income`, `Age`,  
  `Employment_Status`, `Missed_Payments`, `Account_Tenure`, and monthly payment records (`Month_1`–`Month_6`).

**Key Findings:**
- **Outliers:** Extremely low credit scores (in the 300s) and anomalies like `Account_Tenure = 0`.  
- **Missing Data:** Implicit nulls in categorical variables (e.g., inconsistent text labels).  
- **Early Risk Indicators:** High `Credit_Utilization`, multiple `Missed_Payments`, and low `Credit_Score`.

---

### **Step 2: Addressing Missing Data & Data Quality Issues**
| Column | Issue Description | Handling Method | Justification |
|---------|------------------|----------------|----------------|
| `Employment_Status` | Inconsistent spellings (e.g., “EMP”, “employed”) | Standardized categories | Ensures clean encoding and consistency. |
| `Income` | Missing values and possible outliers | Median imputation (grouped by Employment Status) | Robust against skew and preserves differences. |
| `Account_Tenure` | Value of 0 despite payment history | Logical imputation (set to minimum plausible 0.5 years) | Maintains data integrity while avoiding drops. |

**Summary:**  
Standardized categorical values, applied robust imputation methods, and corrected logical inconsistencies to prepare for modeling.

---

### **Step 3: Detecting Patterns and Risk Factors**
**High-Risk Indicators:**
- **High Credit Utilization (≥ 80%)** → Customers close to their credit limits.  
- **Recent Missed Payments (Month_5/Month_6)** → Strong short-term risk signal.  
- **Low Credit Score (< 580)** → Consistently linked to higher default probability.  
- **High Debt-to-Income Ratio** → Indicates financial strain.  
- **Rapid Increase in Loan Balance** → Suggests borrowing under stress.

**Unexpected Findings:**
- Records with `Account_Tenure = 0` but full payment history.  
- Inconsistent “Late” vs. “Missed” payment coding in monthly columns.

**Feature Engineering Recommendations:**
- Create **rolling-window payment behavior features** (e.g., missed payments in the last 3 months).  
- Derive **utilization trend features** to capture changes in financial stress.  
- Add **missing value flags** for model interpretability and transparency.

---

## ⚙️ Tools & Techniques
- **Data Analysis:** Python, Pandas, Excel  
- **Visualization:** Matplotlib, Seaborn, Tableau (optional exploratory visuals)  
- **Model Preparation:** Data cleaning, imputation, feature engineering, and correlation analysis.  

---

## 📊 Key Insights Summary
- **Top Predictors:** `Missed_Payments`, `Credit_Score`, and `Credit_Utilization`  
- **Core Insight:** Behavioral variables (payment history and utilization) carry more predictive power than demographic factors.  
- **Outcome:** Dataset is fully cleaned, standardized, and ready for predictive model training (e.g., Logistic Regression, XGBoost).  

---

## 🚀 Next Steps (Model Planning)
- Train and compare **Logistic Regression** and **XGBoost** for delinquency prediction.  
- Evaluate using **AUC-ROC**, **F1 Score**, and **Recall** for high-risk identification.  
- Perform **fairness analysis** to ensure unbiased predictions across demographic groups.  

---

## 🏁 Outcome
This project delivers a clean, consistent dataset and an analytical foundation for **credit delinquency risk prediction**.  
It provides clear insights into customer financial health and supports proactive intervention strategies for high-risk segments.

---

## 👨‍💻 Author
**Shubham Kuril**  
📧 Email: — surywanshishubham49@gmail.com 
🌐 GitHub: [https://github.com/SHUB0409](https://github.com/SHUB0409)
