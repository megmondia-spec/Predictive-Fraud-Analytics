**Predictive Fraud Analytics**
**Overview**

This project focuses on predicting high-risk credit card transactions to minimize fraud while avoiding unnecessary disruptions to legitimate users. Using a dataset of 10,000 transactions, we built and compared Logistic Regression and Decision Tree models, prioritizing recall and ROC-AUC due to severe class imbalance.

**Problem Statement**

Financial institutions face significant losses from credit card fraud. Overly aggressive detection can frustrate customers. The goal is to identify fraudulent transactions early, helping fraud teams prioritize interventions while maintaining a positive customer experience.

**Key Questions Addressed:**

How effectively can we identify fraudulent transactions early while minimizing unnecessary disruptions?

When should the model be relied upon, and when should human review be preferred?

What proportion of fraud can be detected at acceptable false-positive levels?

Does transaction amount influence fraud likelihood, and can thresholds help prioritize review?

**Data**

Source: Kaggle, Credit Card Fraud Detection Dataset

Size: 10,000 transactions, 9 features + target (is_fraud)

Features:

Numeric: amount, transaction_hour, device_trust_score, velocity_last_24h, cardholder_age

Binary: foreign_transaction, location_mismatch

Categorical: merchant_category (Electronics, Grocery, Food, Travel, Clothing)

**Methodology**

Exploratory Data Analysis (EDA)

Severe class imbalance: 151 fraud vs 9,849 legitimate transactions

Skewed transaction amounts

Fraud concentrated in certain merchant categories

Feature Engineering

Dropped transaction_id

Scaled numeric features

One-hot encoded merchant_category

Modeling

Logistic Regression: Baseline interpretable model

Decision Tree: Captures non-linear relationships, tuned hyperparameters

**Evaluation Metrics**

Recall: Priority metric to detect as much fraud as possible

ROC-AUC: Measures discriminative power across thresholds

Confusion Matrix & F1-score: Support insights for false positives

**Results**
Model	Accuracy	Recall (Fraud)	ROC-AUC
Logistic Regression	0.9585	1.00	0.9933
Decision Tree	0.9670	1.00	0.99997

Decision Tree outperformed Logistic Regression in ROC-AUC and recall.

Accuracy is less meaningful due to severe class imbalance.

**Business Recommendations**

Deploy model in real-time transaction monitoring

Flag top 1–2% high-risk transactions for review

Use fraud probability thresholds dynamically during high-risk periods

Merchant categories with elevated fraud may need stricter authentication

Future Improvements

Ensemble models (Random Forest, XGBoost)

Threshold optimization for better trade-off between recall and false positives

Periodic retraining to adapt to evolving fraud patterns

