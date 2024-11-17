# ML project with data analysis

Table of Contents
- help
- help
- help

## Project Background
Health insurenth is big part of USA economy going to be influesed more by AI technologys. Collected data have to help improve business proces and provide insieghts on price-building. 
***

## EDA
This dataset contains 1338 rows of insured data, where the Insurance charges are given against the following attributes of the insured: Age, Sex, BMI, Number of Children, Smoker and Region. There are no missing or undefined values in the dataset. Data head:
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/head(10).png)

* Age rate 18-64
* Dependent(children) from 0 to 5 added to Health Insurance
* Avarege charges **13270.42$** Min: **4740.28$** Max: **63770.42$**

To explore tmhe data, we will create a dashboard that represents our features and allows us to compare them.
Data is well represented. We dont see any incline beyond male and famale. The youngest group slightly bigger then other. 
Geographicly data represented almost equeal. The future smoker going to be so influence on variable and create visiable 3 clusters.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Dashboard.png)
***

## ML process
### Data preparation
Not numerical data should be converted to numerical. 
We apply One-Hot Encoding (or we can use get_dummies) for not ordinal categorical feature:
* "sex"
* "region"
Ordinal data will be encoded using LabelEncoder:
* "smoker" (0 for non-smoker)

As data have only 10 fetures we keep all for build model. 
Corelation matrix shows that "smoker," "bmi," and "age" are highly correlated with our charges-target variable.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Data%20corelation.png)

### Model evaluating 

We use the R² score (coefficient of determination) to evaluate models.

For this regeresion task we start from:
* Random Forest Regressor:
    - Best cross-validated score: **0.8571**
    - Test R^2 score: **0.8794**
* Ridge:
    - Best cross-validated score: **0.7389**
    - Test R^2 score: **0.7836**

As expected Ridge dont feet data well and shows worse performance. While Random Forest Regressor show expected good result for non-linar relatishion.

* XGBRegressor:
  - Best cross-validated score: **0.8576**
  - Test R^2 score: **0.8834**
* GradientBoostingRegressor:
  - Best cross-validated score: **0.8565**
  - Test R^2 score: **0.8802**

Chart will help repraesent evaluation.
![alt](https://github.com/RNanko/Health-insurance-Project)

After evaluating four models, we will keep two for the final MAE and RMSE comparison.
XGBoost: 
MAE: 2454.8804, 
RMSE: 4254.1989
RandomForest: 
MAE: 2474.3144, 
RMSE: 4327.7243

The winner is XGBoost, which we can use to predict insurance costs based on our chosen parameters. Let's try to predict self-insurance costs.
Best practice is always _GRID!_ 














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
