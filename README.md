# Credit Card Fraud Detection

## Problem Statement
Given a historical set of labeled credit card transactions, the objective is to build a classification model that can identify fraudulent transactions as accurately as possible while keeping false positives under control. This is a binary classification problem with highly imbalanced data.

## Dataset
- **Source**: [Credit Card Fraud Detection - Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Samples**: 284,807 transactions, 492 fraudulent (0.172%)
- **Features**: 30 anonymized features (V1–V28, Time, Amount)
- **Target**: Class (0=legitimate, 1=fraud)

Item	Description
Dataset name	Credit Card Fraud Detection
Source / URL	Kaggle – MLG-ULB creditcardfraud dataset
Task type	Binary classification
Number of samples	284,807 transactions
Fraudulent samples	492 transactions
Legitimate samples	284,315 transactions
Fraud ratio	0.172% of all transactions
Number of columns	31 columns in total
Input features	30 input variables: Time, Amount, and V1–V28
Target label	Class (0 = legitimate transaction, 1 = fraudulent transaction)
Data characteristics	Highly imbalanced, anonymized, all-numeric dataset suitable for supervised ML experiments


## Methods
We implemented and compared:
- Logistic Regression
- Random Forest

## Preprocessing & Validation
- Handling class imbalance with SMOTE (applied correctly only on training data)
- Train/test split: 80/20
- Cross-validation: 5-fold (with leakage issue observed – discussed in report)

## Evaluation Metrics
- Accuracy, Precision, Recall, F1-score, ROC-AUC, AUPRC

## Results
- Random Forest achieved much better balance (F1=0.828) than Logistic Regression (F1=0.10).
- ROC-AUC was misleading (~0.96 for both), but AUPRC showed clear difference (0.816 vs 0.715).
- Cross-validation was overly optimistic due to SMOTE applied before splitting; test set gives more reliable results.
