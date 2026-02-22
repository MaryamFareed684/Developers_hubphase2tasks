# Customer Churn Prediction - ML Pipeline

## Objective
The objective of this project is to build a production-ready end-to-end machine learning pipeline to predict customer churn using the Telco Customer Churn dataset.

## Dataset
Telco Customer Churn dataset containing customer demographics, account information, and churn status.

## Methodology

1. Data Cleaning and Preprocessing
   - Removed unnecessary columns
   - Handled missing values
   - Encoded categorical features
   - Scaled numerical features

2. Model Development
   - Logistic Regression
   - Random Forest Classifier

3. Hyperparameter Tuning
   - Used GridSearchCV with 5-fold cross-validation

4. Evaluation Metrics
   - Accuracy
   - Precision
   - Recall
   - F1-score
   - Confusion Matrix

5. Model Export
   - Saved final pipeline using joblib for deployment

## Key Results
- Random Forest achieved better performance compared to Logistic Regression.
- The model successfully predicts customer churn with optimized hyperparameters.
- The pipeline is reusable and production-ready.

## Technologies Used
- Python
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

