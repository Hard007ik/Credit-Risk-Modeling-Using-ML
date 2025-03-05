# About dataset:
https://github.com/Hard007ik/Credit-Risk-Modeling-Using-ML/blob/main/datasets/Features_Target_Description.xlsx

# Overview
This project aims to develop a robust Machine Learning model for credit risk assessment, focusing on feature selection, statistical analysis, and data preprocessing techniques to identify significant factors influencing loan approval decisions.


## Key Features and Workflow
### Feature Selection:

Categorical features were analyzed using the Chi-Square Test to determine their association with the target variable (Approved_Flag).

Features such as MARITALSTATUS, EDUCATION, GENDER, last_prod_enq2, and first_prod_enq2 showed significant associations (p-value < 0.05).

Numerical features were examined for multicollinearity using Variance Inflation Factor (VIF).

Highly correlated features (VIF > 6) were removed to improve model performance.

Further statistical checks using ANOVA ensured only informative features were retained.

Preprocessing:

Categorical data was encoded using Label Encoding for ordinal variables like EDUCATION and One-Hot Encoding for nominal variables such as MARITALSTATUS and GENDER.

Final feature set included a combination of categorical and numeric variables critical for the prediction task.

## Model Development and Evaluation
Several models were trained and evaluated for their performance on the test dataset:

Random Forest Classifier
Train Accuracy: 99.99%

Test Accuracy: 76.39%

Strength: High precision and recall for majority classes.

XGBoost Classifier
Train Accuracy: 88.99%

Test Accuracy: 77.83%

Strength: Balanced performance across all classes with fine-grained control through hyperparameter tuning.

Decision Tree Classifier
Train Accuracy: 99.99%

Test Accuracy: 70.35%

Limitation: Overfitting due to exhaustive splits on the training data.

Logistic Regression
Train Accuracy: 74.41%

Test Accuracy: 74.17%

Strength: Simplicity and interpretability.

K-Nearest Neighbors (KNN)
Train Accuracy: 72.71%

Test Accuracy: 62.05%

Limitation: Poor performance due to high dimensionality of the dataset.

## Hyperparameter tuning of XGBoost
param_grid = {
    'n_estimators': [50, 100, 150, 200],
    'max_depth': [3, 5, 7, 10],
    'learning_rate': [0.01, 0.05, 0.1, 0.2],
    'subsample': [0.5, 0.8, 1.0],
    'reg_lambda': [1, 4, 7, 10],
    'reg_alpha': [1, 4, 7, 10]
}

Best Hyperparameters: {'learning_rate': 0.2, 'max_depth': 3, 'n_estimators': 150, 'reg_alpha': 1, 'reg_lambda': 10, 'subsample': 0.5}
Train Accuracy: 0.800332828147752
Test Accuracy: 0.7802210864138833
