# ML project with data analysis

Table of Contents
-
-
-

## Project Background
Health insurenth is big part of USA economy going to be influesed more by AI technologys. Collected data have to help improve business proces and provide insieghts on price-building. 

## Executive Summary
This dataset contains 1338 rows of insured data, where the Insurance charges are given against the following attributes of the insured: Age, Sex, BMI, Number of Children, Smoker and Region. There are no missing or undefined values in the dataset. Data head:
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/head(10).png)

* Age rate 18-64
* Dependent(children) from 0 to 5 added to Health Insurance
* Avarege charges **13270.42$** Min: **4740.28$** Max: **63770.42$**

## EDA
To explore tmhe data, we will create a dashboard that represents our features and allows us to compare them.
Data is well represented. We dont see any incline beyond male and famale. The youngest group slightly bigger then other. 
Geographicly data represented almost equeal. The future smoker going to be so influence on variable and create visiable 3 clusters.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Dashboard.png)
































Please checkData set: https://www.kaggle.com/datasets/teertha/ushealthinsurancedataset/data
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

  
***
Please checkData [set](https://www.kaggle.com/datasets/teertha/ushealthinsurancedataset/data).
