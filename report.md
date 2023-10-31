# Module 12 Report Template

## Overview of the Analysis

Analyzing lending data for a theoretical fincancial institution using machine learning. The data included the loan size, interest rate, the borrower's income, their debt to income ratio, number of accounts, derogatory marks, and total debt. The goal is to predict which loans will be healthy or high-risk. I first isolated the loan_status column into a separate list and removed it from the main dataframe. I then separated the sample data into training data and testing data, trained the model on the training data using LogisticRegression, used that model to predict the loan_status of the test data, then compared it to the actual values using a confusion matrix and classification report. I then created a second model using the same data and used RandomOverSampler to see if this would improve the predictions.

## Results

* Machine Learning Model 1:
  * Overall the model is 99% accurate.
  * Precision for healthy loan predictions is 1.00, this means that almost everything predicted to be healthy was healthy.
  * Precision for high-risk predictions is 0.85, meaning 15% of the loans predicted to be high-risk were actually healthy.
  * Recall for healthy loans is 0.99, so the model correctly identified 99% of the healthy loans.
  * Recall for high-risk loans is 0.91, which means out of all the high risk loans, 9% were predicted to be healthy.
  
  At first I thought the recall for high-risk loans contradicted the precision for healthy loans being 100%, but it does not. Healthy loans precision is actually 99.7% and the classification report is rounding up.

* Machine Learning Model 2:
  * Overall the model is 99% accurate.
  * Precision for healthy loan predictions is 1.00, this means that almost everything predicted to be healthy was healthy.
  * Precision for high-risk predictions is 0.84, meaning 16% of the loans predicted to be high-risk were actually healthy.
  * Recall for healthy loans is 0.99, so the model correctly identified 99% of the healthy loans.
  * Recall for high-risk loans is 0.99, which means out of all the high risk loans, 1% were predicted to be healthy.

## Summary

If you are using one of these models to decide whether a loan is healthy or high-risk and avoiding high-risk loans is very important, then I would recommend using Model 2. Model 2 had a very small drop in high-risk precision for a large gain in high-risk recall, which I think is more important for a lender that wants to take on as few high-risk loans as possible.

Both models have excellent precision and recall for healthy loans. Model 2 is very close to the same precision for high-risk loans (84% vs 85%), but it has much better recall for high-risk loans at 99% vs 91% for Model 1.

In other words, for both models 15% and 16% of what they predict to be high-risk loans are not actually high-risk, but for Model 1 9% of actual high-risk loans will be missed and Model 2 1% of actual high-risk loans will be missed.