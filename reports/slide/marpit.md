---
marp: true
theme: default
paginate: true
---

# Predicting Customer Churn in Telecom: A Machine Learning Approach  
### By Hans Darmawan - JCDS2602  

---

# 1. Business Understanding

- XYZ Company is a leading telecommunications provider facing challenges related to customer churn, impacting revenue and growth.
- Customer churn is the rate at which customers discontinue using telecom services, affecting profitability.
- Churn is the opposite of customer retention and critical in subscription-based services.
- High churn rates lead to financial losses; retaining customers is cheaper than acquiring new ones.
- XYZ Company aims to leverage data analytics and machine learning to predict and reduce churn.

---

# 1.2 Gap Analysis and Problem Statements

- No current predictive model to identify at-risk customers limits retention strategies.
- Gaps in data quality, stakeholder engagement, model interpretability, and workflow integration.
- Problem statements:
  - Which customers are likely to churn?
  - What factors influence churn?
  - How to reduce churn?

---

# 1.4 Goals and Analytical Approach

- Develop a predictive model to classify churn vs no churn using machine learning.
- Identify key features influencing churn to optimize retention strategies.
- Provide actionable insights for business to reduce churn.
- Approach includes business understanding, data exploration, preparation, modeling, evaluation, and deployment.

---

# 1.6 Metric Evaluation and Success Criteria

- Business metric:  
  Churn rate = (Customers Lost / Total Customers) * 100%
- Machine learning metric:  
  Recall = TP / (TP + FN), critical to capture at-risk customers.
- Success criteria:  
  Recall ≥ 80%, reliable prediction, interpretable insights.

---

# 2. Data Understanding

- Dataset: 4,930 entries, 11 columns including tenure, monthly charges, contract type, and churn status.
- No missing values; 77 duplicated rows retained after assessment.
- Object columns converted to categorical for better analysis.
- Churn distribution: 26.7% churned, 73.3% stayed — class imbalance present.

---

# 2.5 Exploratory Data Analysis Highlights

- Average tenure ~32 months; monthly charges average ~64.88 units.
- Customers with dependents less likely to churn than those without.
- Fiber optic users have highest churn rate (~42.2%).
- Month-to-month contracts show highest churn (~43.3%).
- Paperless billing users churn more (~33.5%) than non-users.

---

# 3. Data Preparation

- Feature engineering:  
  Created TotalCharges = tenure * MonthlyCharges to capture cumulative revenue.
- Target variable 'Churn' mapped to binary (Yes=1, No=0).
- Stratified train-test split (80-20) preserves class distribution.
- Preprocessing pipelines set up for scaling, encoding, and binary mapping.

---

# 4. Modeling and Evaluation

- Evaluated classifiers: Logistic Regression, Random Forest, SVM, AdaBoost, ensemble stacking.
- AdaBoost with RobustScaler achieved best recall (~54.2%) in cross-validation.
- Hyperparameter tuning improved recall to ~88.9% using ADASYN resampling and tuned AdaBoost.
- Final model recall on test data: 0.9202 — strong churn identification.

---

# 4.4 Learning Curve and Threshold Tuning

- Learning curve shows stable training and validation recall — good fit, no overfitting.
- Precision-Recall curve threshold tuning found threshold 0.1192 with recall 1.0.
- Threshold tuning considered "No Go" due to potential overfitting and unrealistic threshold.

---

# 5. Model Interpretation and Performance

- LIME shows 'Contract' as strongest positive contributor to churn prediction.
- Other key features: InternetService_Fiber optic, PaperlessBilling, tenure (negative impact).
- Confusion matrix: model correctly predicts majority of churn and no churn cases.
- Predicted churn rate (26.67%) closely matches actual (26.69%) — good calibration.

---

# 6. Deployment

- Model saved with joblib for future use.
- Instructions for loading model and predicting churn on new customer data.
- Example scenarios demonstrate effective churn probability prediction.
- Limitations: dependent on data quality, potential overfitting, need for regular updates.

---

# 7. Conclusion and Recommendations

- Contract type strongly influences churn; longer contracts reduce churn risk.
- Fiber optic and paperless billing users have higher churn risk; improve services.
- Engage new customers; promote device protection and online security services.
- Balance precision and recall in tuning; retrain model regularly to adapt to changes.

---

# Thank You  
Questions?
