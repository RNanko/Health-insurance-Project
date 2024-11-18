# ML project with data analysis

## Table of Contents
- [Project Background](#project-background)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Machine Learning Process](#machine-learning-process)
    * [Model Evaluation](#model-evaluation)
    * [Feature importances](#feature-importances)
- [Results](#results)
- [Recommendations](#recommendations)
- [Dataset](#dataset)



## Project Background
Health insurance is a significant part of the U.S. economy and is poised to be further influenced by AI technologies. This project analyzes health insurance data to improve business processes and provide insights into price modeling.
***

## EDA
The dataset contains 1,338 rows of insured data, including attributes such as age, sex, BMI, number of children, smoking habits, and region. The target variable is the insurance charges. There are no missing values.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/head(10).png)

Key insights:
Age range: 18–64 years
Number of dependents: 0–5
Average charges: $13,270.42 (Min: $4,740.28; Max: $63,770.42)

To understand the dataset, an interactive dashboard was created. It highlights the distribution of features and reveals clusters influenced by smoking habits.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Dashboard.png)
***

## ML process
### Data preparation
Non-numerical features were encoded:
One-Hot Encoding for categorical features: sex, region.
Label Encoding for ordinal features: smoker.
Correlation analysis revealed that smoker, bmi, and age are the most significant predictors of charges.

As data have only 10 fetures we keep all for build model. 
Corelation matrix shows that "smoker," "bmi," and "age" are highly correlated with our charges-target variable.
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Data%20corelation.png)

### Model evaluation 

We evaluated models using the R² score to measure their ability to predict charges accurately.

For this regeresion task we start from:
* Random Forest Regressor:
    - Best cross-validated score: **0.8571**
    - Test R^2 score: **0.8794**
* Ridge:
    - Best cross-validated score: **0.7389**
    - Test R^2 score: **0.7836**

As expected Ridge dont feet data well and shows worse performance. While Random Forest Regressor show expected good result for non-linar relatishion.

* XGBoost:
  - Best cross-validated score: **0.8576**
  - Test R^2 score: **0.8834**
* GradientBoostingRegressor:
  - Best cross-validated score: **0.8565**
  - Test R^2 score: **0.8802**

Comparison of model scores:
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Model%20Scores%20Comparison.png)

Final Evaluation:
After testing, XGBoost outperformed the other models with the best Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE):
MAE: $2,454.88
RMSE: $4,254.20
***

### Feature importances 

Using the feature importance module, we determined the most influential variables:
![alt](https://github.com/RNanko/Health-insurance-Project/blob/main/Visualizations/Most%20important%20feature.png)
Health-related attributes like smoker and bmi were identified as the most critical.
***

## Results
Sample Prediction:
The predicted value for a test individual was **$6,046.76**, compared to the actual charge of **$5,272.18**. 
This difference arises because machine learning models are approximations—they attempt to find patterns in data and make predictions based on these patterns.

Key Points:
* MAE of **$2,454.88** indicates that most predictions are relatively close to the true charges.
* RMSE of **$4,254.20** suggests that while most predictions are accurate, some errors are much larger (outliers), which pull the RMSE value higher.
* Factors Influencing the Result: Features like smoker, bmi, age, and the number of children heavily influence the insurance charge. Any slight deviation in these features (or the way they interact) can affect predictions.
* Residual Error: No model is perfect. This small gap reflects real-world variability and the inherent limitations of the training data or the model.

This project successfully demonstrates how machine learning can predict health insurance charges by leveraging key features. It highlights the potential of AI to transform the insurance industry by providing insights into cost drivers and enabling personalized premium calculation. However, for broader applicability, further data enrichment and fine-tuning are recommended.
***

## Recomendation

Enhance Smoking Policies: 
* As smoking status significantly impacts charges, insurance companies should implement tailored plans for smokers and non-smokers.
* Data Augmentation: Future datasets should include additional health metrics like pre-existing conditions or lifestyle habits for better predictions.
* Use Grid Search or Randomized Search: For hyperparameter tuning to further optimize models like Random Forest or XGBoost.
***

Please check [Data](https://www.kaggle.com/datasets/teertha/ushealthinsurancedataset/data).
Pleas check [Jupyter Notebook](https://github.com/RNanko/Health-insurance-Project/blob/main/Health%20Insurance%20project.ipynb)

Thank you for attention.
