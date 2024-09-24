# Employee Turnover Prediction Model
## Overview
- This project aims to predict employee turnover using a dataset containing various employee-related features. We employ multiple machine learning algorithms, perform preprocessing steps, handle class imbalance using SMOTE, and evaluate the models using cross-validation and hyperparameter tuning. The goal is to build a robust model capable of identifying employees likely to leave the company.

## Data
- The dataset used is employees_data.csv (attached to the notebook).
- Features include both categorical (e.g., salary, department) and numerical (e.g., satisfaction level, last evaluation).
- The target variable: left.
  
## Exploratory Data Analysis (EDA)
Data Overview:
- No missing values were found in the dataset.
- Two features are categorical, while the rest are numerical.
- Distribution of Numerical Features: Histograms with KDE plots are used to inspect the distribution of the numerical columns.
- Outlier Detection: Boxplots reveal outliers in the tenure feature.
- Pairwise Feature Relationships: A pair plot indicates that the features are not linearly separable.
- Class Imbalance
The dataset contains imbalanced classes, with fewer instances of employees who left the company. SMOTE  is used to balance the classes in the training set.

## Data Preprocessing
- Encoding:
    - Ordinal encoding for the salary column due to its ordered nature.
    - One-hot encoding for the department column due to its low cardinality and lack of inherent order.

- Scaling: The RobustScaler is applied to the numerical features to handle outliers effectively.

## Model Building
- We used the following machine learning models:
     - Logistic Regression
     - Support Vector Classifier (SVC)
     - Decision Tree Classifier
     - Random Forest Classifier

## Model Evaluation
- Models were evaluated using 5-fold cross-validation, and metrics such as accuracy, precision, recall, F1 score, and AUC were computed.
- The best-performing model: RandomForest.
- Handling Overfitting:
    - The Random Forest model showed overfitting, with a perfect training accuracy but slightly lower test accuracy.
- Hyperparameter tuning using  was performed using RandomizedSearchCV to improve the model's performance and address overfitting.
- After tuning, the model showed improved generalization and reduced overfitting.
  
## Feature Importance
- Feature importance analysis revealed that certain features, such as department_accounting, department_hr, and department_marketing, had minimal influence on the model’s prediction.
  
## Model Evaluation and Visualization
- Confusion Matrix.
- Classification Report.
- Insights:
     - The precison score was better than the recall score.
- ROC Curve and AUC Score: The ROC curve shows the model’s ability to separate the classes, with an AUC score close to 1, indicating a good performance.
  
## Conclusion
- The Random Forest model, after tuning, is highly effective at predicting employee turnover, with a high true positive rate and low false positive rate. 
- This model can help HR departments proactively address factors contributing to employee turnover.


## Future enhancement
- Explore other ensemble methods like Gradient Boosting or XGBoost.
