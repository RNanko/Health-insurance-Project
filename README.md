# Health-insurance-Project
Data set: https://www.kaggle.com/datasets/teertha/ushealthinsurancedataset/code
Health Insurance Cost Prediction
This project focuses on predicting health insurance costs based on individual attributes using machine learning models. The dataset includes six features: age, sex, BMI, children, smoker status, and region, with "charges" as the target variable.

Project Steps
Exploratory Data Analysis (EDA):
- Visualized data distribution and identified clusters.
- Observed that smokers tend to have higher charges.
- Ensured data balance with an equal number of male and female samples.

Data Preprocessing:
  Encoded categorical features:
  * Used OneHotEncoder for "sex" and "region."
  * Used LabelEncoder for "smoker" (0 for non-smoker, 1 for smoker).
- Identified strong correlations between "charges" and features like "smoker," "BMI," and "age."

Model Training:
- Initially tested basic models: Random Forest Regressor and Ridge Regression.
- Advanced to XGBRegressor and Gradient Boosting Regressor for improved accuracy.
- After evaluation, selected XGBoost for the best MAE and RMSE performance.

Results and Insights:
-Created feature importance and EDA dashboards to confirm insights.
- Established a robust model to predict health insurance costs accurately based on user-provided parameters.
