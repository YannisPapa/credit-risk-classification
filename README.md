# credit-risk-classification

This is my submission for Module 20 Challenge with Berkeley Data Analytics Boot Camp.

lending_data.csv data file in the Resources folder is used in credit_risk_classification.ipynb.

Running credit_risk_classification.ipynb will give you a notebook that uses a Logistic Regression Model to find out if a load will be a 0 (healthy loan) and 1 (high-risk loan). Also an analysis of the machine learning model and how it performed is provided.

## Overview of the Analysis

### Purpose of the Analysis
The purpose of this analysis was to evaluate Machine Learning Logistic Regression Model to predict the likelihood of a loan being classified as "high-risk" (1) or "healthy" (0). Accuracy in this context is critical for lenders looking to assess financial risks and make decisions about loan approvals.

### Explanation of the Financial Information in the Data
The dataset used for training the machine learning model contained the following financial features:

* Loan Size (loan_size): The total amount of the loan requested by the borrower. Larger loan sizes may correlate with higher financial risk, especially if the borrower's income or financial stability cannot support repayment.

* Interest Rate (interest_rate): The percentage of the loan amount charged as interest by the lender. High-risk loans often carry higher interest rates to compensate for the increased risk of default.

* Borrower Income (borrower_income): The annual income of the borrower. This is a critical indicator of the borrower's ability to repay the loan. Higher incomes generally reduce the risk of default.

* Debt-to-Income Ratio (debt_to_income): The ratio of the borrower’s total monthly debt payments to their monthly income. A high debt-to-income ratio suggests that a borrower may be over-leveraged and poses a higher risk.

* Number of Accounts (num_of_accounts): The total number of financial accounts held by the borrower (e.g., credit cards, loans, etc.). More accounts can indicate financial stability or, conversely, a higher risk if too many are open and actively used.

* Derogatory Marks (derogatory_marks): The number of negative records on the borrower’s credit history, such as defaults or late payments. A higher number of derogatory marks directly signals higher credit risk.

### Prediction Objective
The goal was to use these financial features to predict whether a loan would be classified as:
0 (Healthy Loan): A loan that is expected to be repaid on time with minimal risk to the lender.
1 (High-Risk Loan): A loan that carries a significant risk of default or late payment, posing potential financial losses for the lender.


## Results

* Logistic Regression Model (`0` (healthy loan) and `1` (high-risk loan)):
    * Accuracy Score : 0.9927259595542716
    * Healthy Loans (`0`):
        * Precision: 1.00
        * Recall: 0.99
        * f1-score: 1.00
    * High-Risk Loans (`1`):
        * Precision: 0.85
        * Recall: 0.95
        * f1-score: 0.89

## Summary

### How did the Logistic Regression Model perform?
The model performed exceptionally well for healthy loans (`0`), with near-perfect precision, recall, and F1-score. For high-risk loans (`1`), while the recall was strong at 95% (indicating that most high-risk loans were correctly identified), the precision of 85% suggests that some healthy loans were misclassified as high-risk.

### Does Performance Depend on the Problem?
Yes, the importance of performance metrics depends on the problem's objectives:

If Predicting High-Risk Loans(`1`) is Critical:
* Recall is the most important metric, as missing high-risk loans can lead to financial losses for the lender. The model's recall of 95% for high-risk loans is strong, making it suitable for this objective.
If Minimizing False Positives for Healthy Loans(`0`) is Critical:
* Precision for high-risk loans becomes essential to avoid incorrectly flagging healthy loans as high-risk. The model's precision of 85% is reasonable, though there is room for improvement.

I would recomend the Logistic Regression Model but only if the lender using it cares more for Predicting High-Risk Loans and is willing to make a few more mistakes with false positives. Otherwise maybe some changes could be made such as stratifying the data to help the model fix its false positives.
