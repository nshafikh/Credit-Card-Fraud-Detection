# Credit Card Fraud Detection: A Machine Learning Approach

## Objective
Classify transactions as fraudulent or non-fraudulent using machine learning

---

## Dataset
- **Source**: [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)  
- **Transactions**: 284,807  
- **Fraudulent Transactions**: 492 (0.172% of all transactions)  
- **Features**:  
  - PCA-engineered features: V1-V28  
  - Additional features: Time, Amount, Class  

---

## Workflow Overview

### **Part 1**: Initial Preprocessing and Model Selection
- **EDA and Preprocessing**: 
  - Standardized the `Amount` feature.
  - Analyzed class imbalance and its implications.
- **Performance Metrics**:
  - Prioritized **Recall** to minimize false negatives (fraudulent transactions missed).  
  - Evaluated models using:
    - Precision-Recall AUC (PR-AUC)
    - F2-Score (Recall-focused metric)  
  - Precision-recall trade-offs examined through PR-Curves.  
- **Algorithms Evaluated**:
  - KNN, Random Forest, XGBoost  
- **Results**:
  - KNN and XGBoost emerged as top-performing models:
    - **KNN**: Best for high recall with reasonable precision (~47%).  
    - **XGBoost**: Best for high precision and balanced metrics (e.g., F2-Score).  

### **Part 2**: Scaling, Balancing, and Advanced Evaluation
- **Feature Scaling**:  
  - Applied StandardScaler to PCA-engineered features.  
  - Unscaled data performed better in 5/6 cases; scaling was not adopted.  
- **Class Balancing**:  
  - Tested **SMOTE** (oversampling) and **undersampling** methods.  
  - Balancing showed mixed results; unbalanced data often yielded better performance.  
- **Final Model Recommendations**:
  - **KNN** (unscaled, original data): Best recall (>86%) with manageable precision drop.  
  - **XGBoost**: Balanced recall and precision.  
  - **LightGBM**: Showed promise when combined with SMOTE but was not explored further.  

---

## Key Findings
1. **Scaling**:
   - Standardization reduced model performance for PCA-engineered features, likely due to over-engineering or information loss.
2. **Balancing**:
   - Improved LightGBM but reduced performance for KNN and Decision Trees.
3. **Model Selection**:
   - KNN and XGBoost trained on imbalanced data and LightGBM trained on SMOTE data emerged as leaders, depending on desired recall/precision balance.  
   - KNN is ideal for maximizing recall (critical for fraud detection).  

---

## Future Steps
- Explore hyperparameter tuning (e.g., Grid Search, Random Search).  
- Investigate additional models (e.g., SVM for undersampled data).  
- Combine SMOTE with LightGBM for deeper evaluation.  
