_**Project Report: Impact of Socioeconomic and Lifestyle Factors on Resilience Prediction**_

**1. Introduction**
In this project, we aim to predict resilience outcomes based on a range of socioeconomic and lifestyle factors using a Gradient Boosting Classifier. The dataset includes features such as Health-related factors (e.g., BMI, HighBP, HighChol, Stroke, etc.) and Socioeconomic factors (e.g., Age, Income, Education). The goal is to identify which factors most strongly influence resilience and predict whether an individual is resilient or non-resilient.

**2. Data Preprocessing**
Before training the model, we performed the following preprocessing steps:

Missing Data Handling: The dataset was checked for missing values, and appropriate imputation techniques were applied where needed.
Feature Encoding: Categorical variables (such as Sex, Smoker, and Education) were encoded using label encoding.
Feature Scaling: Numerical features were scaled using standardization to improve model performance and convergence speed.
SMOTE Application: Given the class imbalance, we used Synthetic Minority Over-sampling Technique (SMOTE) to generate synthetic samples for the minority class (Resilient), balancing the dataset.

**3. Model Selection**
We employed several machine learning models to predict resilience, focusing on the Gradient Boosting Classifier for its robustness and ability to capture complex patterns in data. The following models were tested:

- Random Forest
- Logistic Regression
- Gradient Boosting

**4. Hyperparameter Tuning**
The Gradient Boosting Model was tuned using GridSearchCV to find the optimal set of hyperparameters, including:

learning_rate
max_depth
n_estimators
Through the grid search, the following parameters were selected:

learning_rate: 0.05
max_depth: 3
n_estimators: 100

**5. Model Evaluation**
After training the model with the optimal hyperparameters, we evaluated its performance using metrics such as Accuracy, F1-Score, AUC-ROC, and a Confusion Matrix.

Final Results
Accuracy: 85%
F1-Score: 0.77 (Resilient class), 0.89 (Non-Resilient class)
AUC-ROC: 0.944
The Confusion Matrix indicated that the model performed well in detecting resilient individuals, though there was a slight tradeoff between precision and recall for the non-resilient class.

**6. Feature Importance Analysis**
The most important features identified by the Gradient Boosting model were:

- RiskFactorScore: A composite score likely capturing multiple health risks, contributing significantly to predictions.
- GenHlth (General Health): Strongly correlates with resilience, suggesting that individuals with poorer general health tend to be less resilient.
- Age: Age showed considerable importance, likely due to its association with various health conditions and resilience.
- DiffWalk (Difficulty Walking): A key indicator of physical resilience, influencing the model's predictions about mobility and overall health.
- BMI: Body Mass Index is a well-known indicator of health and a key factor in predicting resilience.
- Sex: Gender differences were significant in determining resilience outcomes.

**7. Model Interpretation**
The Gradient Boosting Model was able to effectively capture the complex relationships between various features and resilience. The most influential features were a combination of both health-related factors (such as BMI, DiffWalk) and socioeconomic factors (such as RiskFactorScore, Income). This aligns with existing literature, which suggests that both physical and economic factors play crucial roles in determining resilience outcomes.

**8. Conclusion**
In this project, we built a robust machine learning model to predict resilience based on socioeconomic and lifestyle factors. The Gradient Boosting Classifier achieved high accuracy and AUC-ROC, with key features like RiskFactorScore, GenHlth, and Age being significant predictors. The model provides valuable insights into the factors that influence resilience, which can be used to inform interventions targeting at-risk populations.
