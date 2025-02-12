# Customer Churn Prediction Using Machine Learning

## Project Overview:

This project focuses on predicting customer churn using a dataset of bank customers. The dataset includes various customer attributes, and multiple machine learning models are applied to classify whether a customer will exit or stay.

After training several models, RandomForestClassifier was selected as the best model, achieving a test accuracy of 84% and an AUC score of 85%.



## Dataset Overview
File: P1_Churn_Modelling.csv

Target Variable: Exited (1 = Customer left, 0 = Customer stayed)

Features:

Category Features -> Surname, Geography, Gender

Numeric Features -> RowNumber, CustomerId, CreditScore, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, EstimatedSalary


## Workflow

1. Data Exploration
 - Read Data: Load the dataset using Pandas.
   
 - Initial Insights:
 .info() → Check data types and missing values.
 .describe() → View summary statistics.
 - No missing values or duplicate records were found.




2. Data Preprocessing
 - Categorical Features: Identified ['Surname', 'Geography', 'Gender'] as categorical.
 - Plotted bar charts for Geography and Gender distributions.
 - Numerical Features: Explored numerical features:
  ['CreditScore', 'Age', 'Tenure', 'Balance', 'NumOfProducts', 'HasCrCard', 'IsActiveMember', 'EstimatedSalary'].
 - Visualized relationships between these features and the target variable (Exited).



   
3. Handling Outliers
 - Used Interquartile Range (IQR) to detect outliers in:
   CreditScore, Age, NumOfProducts.
   
 - Applied mean and median imputation to handle outliers using functions:
  detect_IQR(), handling_outliers_median(), handling_outliers_mean().




4. Feature Engineering
 - Feature Selection: Removed irrelevant columns:
 drop(columns=['Surname', 'RowNumber', 'CustomerId']).

   Encoding:
 - Binary encoding for Gender (Male=0, Female=1).
 - One-hot encoding for Geography using pd.get_dummies().


   
5. Data Splitting & Scaling
 - Train-Test Split: 80% training, 20% testing (Exited as the target variable).
 - Feature Scaling: Applied StandardScaler to:
   ['Balance', 'CreditScore', 'Age', 'Tenure', 'EstimatedSalary'].


   
6. Model Selection & Evaluation
   
 - Since the dataset is imbalanced, we used class_weight='balanced' to adjust for class distribution.

 - Trained multiple models:

   Logistic Regression
   
   K-Nearest Neighbors (KNN)
   
   Naive Bayes
   
   Support Vector Machine (SVM)
   
   Random Forest

   
 - Best Model: RandomForestClassifier


 - Evaluate models using:

    Accuracy, Precision, Recall, F1-score, AUC-ROC

    Confusion Matrix & Classification Reports



## Visualization & Insights

✔ Heatmaps
![pic](https://github.com/user-attachments/assets/d26a3508-8a35-4211-822a-8e84599cef1e)


✔ AUC Curve

![pic](https://github.com/user-attachments/assets/f59f0b42-8830-4f38-94d0-35e5f487569a)


✔ Confusion Matrix

![pic](https://github.com/user-attachments/assets/3edaf7d9-b52f-45c4-9aeb-9758f44afede)


✔ Outliers 

![pic](https://github.com/user-attachments/assets/3cc03bb5-d8d6-4231-a975-4b8cc6490564)

![pic](https://github.com/user-attachments/assets/2a2e9456-12a2-4cc6-ae42-3eb0e9e9cf4e)




## How to Run the Project

 - Install Dependencies:
    pip install -r requirements.txt

 - Run Preprocessing & Training:
     python main.py

