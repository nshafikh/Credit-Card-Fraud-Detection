# Credit-Card-Fraud-Detection
## Objective
Classify transactions as fraudulent or non-fraudulent using machine learning.

Dataset
Source: Kaggle Credit Card Fraud Detection dataset

Number of transactions: 284,807

Fraudulent transactions: 492 (0.172% of all transactions)

Features: time, V1-V28 (PCA features), amount, class

## Action plan
Part 1:

Take care of EDA and the bulk of the data preprocessing
Establish performance metrics for our problem
Begin modeling with minimal tuning

Part 2:

Apply universal scaling on all features (including the PCA-engineered features)
Compare model performance and decide whether we should proceed with scaled or unscaled data
Apply data balancing techniques and see if model performance improves
Select best algorithms to move forward with
Using the top performing algorithm and balancing/scaling technique combinations, tune them
