# Predicting Customer Churn in Telecom: A Machine Learning Approach
By Hans Darmawan - JCDS2602

## Project Shortcut Links

- Notebook Link           : 
    + https://github.com/hansdarmawann/telco-churn/blob/main/notebooks/1.2-hdr-init-nb.ipynb
- Saved Best Model Link   : 
    + https://github.com/hansdarmawann/telco-churn/blob/main/notebooks/models/best_tuned_pipeline.joblib

## Project Overview

### 1. Business Understanding  
This project addresses the critical issue of customer churn in the telecom industry, which directly impacts revenue and business growth. The objective is to develop predictive models that accurately identify customers at risk of churning. By analyzing key factors influencing churn, the project aims to provide actionable insights to improve customer retention. A structured analytical approach is adopted, with model evaluation focusing on recall to ensure high performance and interpretability.

### 2. Data Understanding  
The dataset is thoroughly explored to assess its structure and quality. It is confirmed to have no missing values, while duplicated rows are identified but retained after careful evaluation. Data types are optimized by converting object columns to categorical types for efficient analysis. Exploratory data analysis uncovers important patterns in customer demographics, service usage, and churn distribution. Relationships among features are examined through visualizations and correlation analysis to guide feature selection and preprocessing.

### 3. Data Preparation  
Data preparation involves engineering a new feature, TotalCharges, representing cumulative customer charges, and encoding the target variable into a binary format. The dataset is split into training and testing sets using stratified sampling to preserve class proportions. Feature types are identified, and preprocessing pipelines are constructed to apply appropriate transformations such as scaling, encoding, and binary mapping. This ensures consistent and efficient data handling during model development.

### 4. Modelling  
Multiple classification algorithms are initialized and evaluated using stratified cross-validation with recall as the primary metric. Different scaling methods are benchmarked to determine the most effective preprocessing approach. An ensemble stacking classifier is included to leverage the strengths of multiple models. Hyperparameter tuning is conducted with a focus on handling class imbalance using advanced resampling techniques and optimizing AdaBoost parameters. The best-performing tuned model is selected based on recall performance.

### 5. Evaluation  
The best-tuned model is evaluated on the test set, achieving high recall scores that demonstrate its effectiveness in identifying churners. Learning curves indicate stable performance without overfitting. Precision-recall curve-based threshold tuning is performed but deemed unsuitable due to potential overfitting risks. Model interpretability is enhanced using LIME, which highlights key features influencing predictions. Confusion matrices provide insights into classification errors, and churn rate comparisons confirm alignment between predicted and actual rates.

### 6. Deployment  
The deployment phase includes saving the final model pipeline using joblib for future use. Guidance is provided on loading the saved model and preparing new customer data for prediction, with example scenarios illustrating practical application. Model limitations are acknowledged, particularly the tendency to overestimate churn due to recall prioritization. Recommendations for business strategies and ongoing model improvements are outlined to support effective implementation.

### 7. Conclusion and Recommendations  
The analysis concludes that contract type, fiber optic Internet service, and paperless billing are significant positive contributors to churn risk. Conversely, longer tenure and protective services such as DeviceProtection and OnlineSecurity reduce churn likelihood. The machine learning model accurately predicts a churn rate of approximately 26.7%, matching the observed rate. Business recommendations include promoting longer-term contracts, improving fiber optic service quality, enhancing paperless billing communication, and implementing personalized retention strategies. Model improvement suggestions emphasize balancing precision and recall through threshold adjustment and ensuring regular retraining to adapt to evolving customer behavior.
