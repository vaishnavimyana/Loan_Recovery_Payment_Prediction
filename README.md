# Loan Recovery: Payment Probability Prediction

 ->Overview

This project builds a machine learning model to predict whether a customer in loan recovery (30+ days past due) will make a payment in a given month.

The goal is to help collection teams prioritize high-probability payers, improving recovery efficiency and reducing wasted effort.

-> Dataset
Source: Internal loan recovery dataset
Volume: ~348,000 account-month records
Time Period: Feb 2023 – Jul 2023
Target Variable: is_payer (derived from Pmt_amount)
         
-> Key Techniques & Approach
Data Cleaning & Feature Engineering
Removed high-missing columns (>80%)
Handled hidden nulls (e.g., CIBIL = 0)
Created loan_age_days feature
Built cibil_missing_flag
Data Leakage Prevention
Removed post-event variables (gwo_amt, dpd_days_wo)
Used time-based split instead of random split
Modeling
Logistic Regression (baseline)
Random Forest (final model)
Class imbalance handled using class_weight='balanced'
Threshold Optimization
Adjusted prediction threshold (0.3 vs 0.5)
Improved recall to capture more potential payers
        
-> Model Performance
Model	ROC-AUC
Logistic Regression	0.75
Random Forest	0.81
Random Forest outperformed baseline by capturing non-linear relationships
Threshold tuning increased recall up to ~88%

-> Key Insights
Delinquency (dpd_days) is the strongest predictor
Loan lifecycle (loan_age_days) significantly impacts repayment behavior
Financial capacity features (EMI, income) have moderate influence
Demographics have relatively low predictive power

-> Business Impact
Enables targeted collection strategies
Improves recovery efficiency by focusing on likely payers
Reduces operational cost by avoiding low-probability accounts
Can be deployed as a payment probability scoring system
