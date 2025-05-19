---
marp: true
theme: default
paginate: true
---

# Predicting Customer Churn in Telecom  
### A Machine Learning Approach  
#### By Hans Darmawan - JCDS2602  

---

# CRISP-DM Overview

- Standard data mining process model  
- Six phases:  
  1. Business Understanding  
  2. Data Understanding  
  3. Data Preparation  
  4. Modeling  
  5. Evaluation  
  6. Deployment  

---

# 1. Business Understanding

- Telecom churn impacts revenue & growth  
- Goal: Identify customers likely to churn  
- Questions:  
  - Who will churn?  
  - Why do they churn?  
  - How to reduce churn?  
- Success metric: Recall ≥ 80%  
- Business impact: Retain customers, reduce costs  

---

# 2. Data Understanding

- Dataset: 4,930 customers, 11 key features  
- No missing values; 77 duplicates retained  
- Churn rate: 27% (imbalanced)  
- Key insights:  
  - Short tenure → higher churn  
  - Month-to-month contracts → highest churn  
  - Fiber optic users churn more  
  - Paperless billing linked to higher churn  

---

# 3. Data Preparation

- Engineered feature: TotalCharges = tenure × MonthlyCharges  
- Converted churn to binary target (Yes=1, No=0)  
- Stratified train-test split (80-20) to preserve class balance  
- Preprocessing pipelines:  
  - Scaling (RobustScaler best)  
  - Encoding categorical & binary variables  
- Addressed class imbalance with oversampling techniques  

---

# 4. Modeling

- Tested multiple classifiers:  
  - Logistic Regression  
  - Random Forest  
  - SVM  
  - AdaBoost (best performer)  
- Used Stratified 5-fold CV with recall scoring  
- Hyperparameter tuning via RandomizedSearchCV  
- Best model: AdaBoost + ADASYN oversampling  
- Test recall: 92% — strong churn detection  

---

# 5. Evaluation

- Learning curve: stable training & validation recall  
- Threshold tuning:  
  - Max recall at low threshold but many false positives  
  - Balanced threshold preferred for business use  
- Model interpretation with LIME:  
  - Contract type strongest churn driver  
  - Fiber optic & paperless billing also important  
- Confusion matrix:  
  - High true positives & true negatives  
  - Some false alarms and missed churners  

---

# 6. Deployment

- Final model saved with joblib for reuse  
- Ready for real-time churn prediction  
- Example predictions:  
  - Customer A: 78% churn risk  
  - Customer B: 13% churn risk  
- Business can target retention efforts efficiently  

---

# Key Business Recommendations

- Encourage longer contracts with incentives  
- Improve fiber optic service quality  
- Enhance paperless billing experience  
- Engage new customers early  
- Promote device protection & online security  

---

# Model Limitations & Next Steps

- Dependent on data quality and representativeness  
- Requires regular retraining with new data  
- Balance recall and precision for cost-effective actions  
- Explore additional features and advanced models  

---

# Thank You!  
Questions?  
