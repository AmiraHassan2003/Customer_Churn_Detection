# Customer Churn Prediction Using Machine Learning

## Project Overview:

This project focuses on predicting customer churn using a dataset of bank customers. The dataset includes various customer attributes, and multiple machine learning models are applied to classify whether a customer will exit or stay.

After training several models, RandomForestClassifier was selected as the best model, achieving a test accuracy of 86% and an AUC score of 84%.



## Dataset Overview
File: P1_Churn_Modelling.csv

Target Variable: Exited (1 = Customer left, 0 = Customer stayed)

Features:

Category Features -> Surname, Geography, Gender

Numeric Features -> RowNumber, CustomerId, CreditScore, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, EstimatedSalary


## Workflow

### 1. Data Exploration
 - Read Data: Load the dataset using Pandas.
   
 - Initial Insights:
 .info() → Check data types and missing values.
 .describe() → View summary statistics.
 - No missing values or duplicate records were found.




### 2. Data Preprocessing
 - Categorical Features: Identified ['Surname', 'Geography', 'Gender'] as categorical.
 - Plotted bar charts for Geography and Gender distributions.
 - Numerical Features: Explored numerical features:
  ['CreditScore', 'Age', 'Tenure', 'Balance', 'NumOfProducts', 'HasCrCard', 'IsActiveMember', 'EstimatedSalary'].
 - Visualized relationships between these features and the target variable (Exited).



   
### 3. Handling Outliers
 - Used Interquartile Range (IQR) to detect outliers in:
   CreditScore, Age, NumOfProducts.
   
 - Applied mean and median imputation to handle outliers using functions:
  detect_IQR(), handling_outliers_median(), handling_outliers_mean().




### 4. Feature Engineering
 - Feature Selection: Removed irrelevant columns:
 drop(columns=['Surname', 'RowNumber', 'CustomerId']).

   Encoding:
 - Binary encoding for Gender (Male=0, Female=1).
 - One-hot encoding for Geography using pd.get_dummies().


   
### 5. Data Splitting & Scaling
 - Train-Test Split: 80% training, 20% testing (Exited as the target variable).
 - Feature Scaling: Applied StandardScaler to:
   ['Balance', 'CreditScore', 'Age', 'Tenure', 'EstimatedSalary'].


   
### 6. Model Selection & Evaluation
   
 - Since the dataset is imbalanced, we used class_weight='balanced' to adjust for class distribution.

 - Trained multiple models:

   Logistic Regression
   
   K-Nearest Neighbors (KNN)
   
   Naive Bayes
   
   Support Vector Machine (SVM)
   
   Random Forest

   
 - Best Model: RandomForestClassifier
 - Best parameters for RandomForestClassifier: {'class_weight': None, 'max_depth': 10, 'min_samples_leaf': 5, 'min_samples_split': 2, 'n_estimators': 100}



 - Evaluate models using:

    Accuracy, Precision, Recall, F1-score, AUC-ROC

    Confusion Matrix & Classification Reports



## Visualization & Insights

### ✔ Heatmaps

![heatmap](https://github.com/user-attachments/assets/2d41bcb1-8f4c-4f5d-999b-7a676a673321)



### ✔ AUC Curve

![roc](https://github.com/user-attachments/assets/2ec11d40-b704-4163-965d-aff09e76c1d8)




### ✔ Confusion Matrix

![confusion](https://github.com/user-attachments/assets/0e7fb5a8-e361-440b-be01-b8548b4b5f61)




### ✔ Outliers 

![outliers1](https://github.com/user-attachments/assets/0ea1312d-2172-4448-a793-d0f3329d2138)

![outliers2](https://github.com/user-attachments/assets/f3f72b16-ef6c-4cb4-abb4-3c2a8e78b1f8)




## How to Run the Project

 - Clone the repository:
 - 
   git clone https://github.com/AmiraHassan2003/Customer_Churn_Detection.git
   
 - Navigate to the project folder:
   cd Customer-Churn-Detection


 - Open the Jupyter Notebook:
  jupyter notebook

 - Run the notebook file main.ipynb

