### Description
This project aims to analyze student performance data to identify key factors influencing academic outcomes.
The primary goal is to explore and model the relationship between various features (like study habits, absences, and demographic factors) and the target variable, GradeClass.

### DATA SOURCE
- Kaggle Dataset

### EDA
- 2392 * 14
- No miissingness
- No outlies
- Target Variable Distribution: Imbalance

### Data Preprocessing
- Feature Scaling: RobustScaler is applied to continuous features (Age, StudyTimeWeekly, Absences) which have a skewed distribution.
- Handling Class Imbalance: SMOTE

### Modeling
- Four models are trained and evaluated:
  - Logistic Regression
  - Support Vector Machine (SVM)
  - Naive Bayes
   - Random Forest
- The performance of each model is assessed using cross-validation, accuracy, precision, recall, and F1 score.
- Best performing model: Random Forest

##### Model Evaluation
- Confusion Matrix: The confusion matrix is visualized to identify common misclassifications.

### HYPEREPARAMETER TUNING
- GridSearchCV is used to fine-tune the Random Forest model.
- Parameters: n_estimators, max_features, max_depth, min_samples_split, min_samples_leaf, bootstrap and class weight.
- Best parameters: Class weight: Balanced
- Comparing Model Performance Before and After Tuning:
    - No change in accuracy.
    - improvement in precision, recall, and F1 score.

### KEY FINDINGS
- Attendance is Crucial.
     - Regular attendance allows students to stay caught up with the coursework, participate in class activities, and benefit from teacher instruction.
     - Investigate the root of the absences.
- Study habits. Frequent focused study leads to better performance.
- Parental Influence:
        - Higher parental education positively impact grades. These parents may provide a rich learning environment.
        - Higher parental support doesn't translate to better grades. This could be due to different reasons such as:
        a) Over-involvement leading to reduced student independence.
        b) High support being a reaction to existing academic struggles.
        c) Poor quality of support may vary.
  - Demographic factors suc as gender and ethnicity are less important in determining student performance.
  - Students involved in extracurricular activities perform worse than those who don't. They could behaving less time and energy to study.

