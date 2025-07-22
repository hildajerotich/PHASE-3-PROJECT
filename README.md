# Churn Prediction — SyriaTel Project
## Overview
This project focuses on predicting customer churn. It dentifies which customers are likely to leave SyriaTel, a telecommunications provider. Churn is a costly problem for telecom companies, and predicting it in advance allows businesses to take proactive measures to retain customers. Using machine learning, we aim to build a classification model that can accurately flag high-risk customers so the company can reduce churn and boost long-term profitability.

## Business and Data Understanding
### Business Problem
In the telecom industry, retaining existing customers is significantly cheaper than acquiring new ones. When customers churn unexpectedly, it often leads to lost revenue and higher marketing costs. If SyriaTel can identify potential churners ahead of time, it can take personalized action such as offering promotions or improving services so as to keep those customers.

### Stakeholder Audience
This project is designed for SyriaTel’s business and marketing teams, especially those responsible for customer retention, loyalty programs, and customer experience. These stakeholders do not need to understand the technical details of machine learning but need clear insights and actionable strategies based on model outputs.

## Dataset Summary
The dataset is publicly available on Kaggle. It contains 21 features describing SyriaTel customers. Each row represents a customer, with features like day, evening and night minutes, day, evening and night calls, day, evening and night charges, international minutes, customer service calls.

The target variable is Churn, which indicates whether or not a customer left the company. The dataset is imbalanced, with significantly more non-churners than churners which is a key factor that is considered in our modeling strategy.

## Modeling
### Approach
We tested several classification models, including Logistic Regression with threshold tuning and ensemble models like XGBoost, to find the best balance between identifying churners and avoiding false alarms. Classification was chosen because the problem is binary; the customer either churns or stays.

## Methodology
Data Preprocessing: Missing values were handled, categorical variables were encoded, and features were scaled or transformed where necessary.

Feature Engineering: We explored creating polynomial features, interaction terms, and log transformations to enhance model performance.

Handling Class Imbalance: Techniques such as adjusting decision thresholds and using XGBoost (which handles imbalance well) were applied.

Model Selection: XGBoost outperformed other models in recall and precision, especially for the minority class (churners), making it our final choice.

## Evaluation
We evaluated models on key classification metrics:

Metric	What It Means	XGBoost Score
Accuracy	Overall correctness	96%
Recall (Churners)	How many actual churners we correctly identified	80%
Precision (Churners)	Of those flagged as churners, how many really were	93%
F1 Score (Churners)	Balance between precision and recall	86%

## Interpretation:
Our final model is highly accurate and reliable in flagging potential churners. It catches most of the customers likely to leave (recall), while minimizing false positives (precision). This ensures that SyriaTel can confidently take action on high-risk customers without wasting resources on those unlikely to leave.

## Conclusion
We successfully built a churn prediction model that:

Identifies 80% of churners before they leave.

Maintains a 93% precision rate, reducing unnecessary customer retention efforts.

Offers SyriaTel a valuable tool for targeted interventions.

The XGBoost model is well-suited for deployment and can be integrated into SyriaTel's CRM system to score customers weekly or monthly. With continued retraining on updated data, the model can adapt to evolving customer behavior and remain a reliable part of SyriaTel’s retention strategy.