# Overview of the Analysis

The objective of this analysis was to develop a supervised machine learning model capable of predicting whether a loan is healthy or high-risk. The dataset utilized consisted of 77,500 records, each containing various attributes related to the loan (such as amount and interest rate) and the borrower's financial status (including income, debt, and accounts), along with a column indicating whether the loan was classified as healthy or high-risk. Out of the total loans, only 2,500 were categorized as high-risk.

The machine learning process was conducted as follows:
## Data Preparation:
- The dataset was divided into labels and features, with the loan status (healthy or high-risk) serving as the label, and the remaining seven columns representing the features.

## Data Splitting:
- The data was split into training and testing datasets.

## Model Selection and Training:
- A Logistic Regression model from the sklearn library was chosen, utilizing the Limited-memory BFGS ('lbfgs') solver. Logistic Regression was selected due to its suitability for binary classification problems, such as determining whether a loan is healthy or high-risk.
- The model was trained using the training data.

## Prediction and Evaluation:
- Predictions were generated using the test data.
- The model's performance was assessed by comparing the predictions with the actual test labels.

## Results

- Accuracy: 0.99
- Balanced Accuracy: 0.95
- Precision
- Healthy: 1.00
- High-Risk: 0.85
- Recall
- Healthy: 0.99
- High-Risk: 0.91
  
## Summary

The Logistic Regression model demonstrates strong performance in predicting healthy loans. However, it incorrectly classifies 10% of high-risk loans as healthy based on the test data. Although none of the loans used for training are for very large amounts (all under $24,000), a loan defaulting early in its term could result in a significant financial loss, potentially outweighing the interest earned from multiple healthy loans.

A notable challenge is the imbalance in the dataset, with very few high-risk loans compared to the number of healthy loans. Increasing the number of high-risk loans in the training dataset could potentially enhance the model's performance.

In the context of loan classification, preventing high-risk loans is more crucial than approving healthy ones, as a single default can incur greater losses than the interest earned from several healthy loans.

## Model Pros and Cons

Pros:
- Excellent prediction accuracy for healthy loans.
- Ample data points for healthy loans.
Cons:
- Limited data points for high-risk loans.
- Loan values capped at $24,000.
- 10% misclassification rate for high-risk loans.

If this model is applied only to loans under $24,000, and if the historical ratio of healthy to high-risk loans is consistent with the dataset (30 to 1), the model may be adequate. Otherwise, due to the increased risk, it would not be recommended. Additionally, the model provides binary classifications (healthy/risky) without offering a probability score, which could be useful for more nuanced decision-making, especially for loans that are borderline.
