# Data Science Midterm Project

## Objectives
This project aims to predict house prices in U.S. based on available features using supervised machine learning techniques. The goal is to gain insights from the data and use data visualization tools to present findings effectively.


## Process
### Step 1: Data Preparation
- **Loading, synthesizing and extracting** : Information from available JSON data files for different cities and states in U.S.
- **Exploratory data analysis** : Uncovering data patterns, spot outliers and learn correlation. 
- **Data cleaning/wrangling** : Handling missing values, removing duplicates, correcting data types, and handling outliers.
- **Feature Engineering** : Creating new columns that may improve model performance.

### Step 2: Model selection and Feature selection
- Training multiple baseline models on the preprocessed data: Linear Regression, Support Vector Machines SVM, Random Forest and XGBoost.
- Gathering evaluation metrics and compare results to pick the best-performing model for hyper tuning.
- Performing feature selection to get a reduced subset of the original features for better model scoring.
- Refitting model with smaller feature subset.
- Evaluating the model performance of dimensionality reduction to decide if it be should include feature selection in your final pipeline.

### Step 3: Hyperparameter tuning and pipeline creation
- Performing hyperparameter tuning on the best performing models from Part 2 and saving the tuned model.
- Building a final prediction pipeline and saving it for future usage.

## Results

### Data Insights
> - Single Family homes are popular among 90% of the dataset which points towards its commonality among different U.S. residents.
> -  **Boston, Honolulu, Nashville and Springfield** cities seems to have high priced housing with an average $1 Million house sale price.
> - Most of the houses in this dataset belongs to cluster with year build from 1900s to 2020s.

### Model Results
- Among the baseline models examined, XGBoost is the best-performing model based on all metrics, with the lowest MAE and RMSE, and the highest R2 as well as Adjusted R2 values despite the existence of overfitting. It is worth considering the Linear regression model because it achieves positive results with no overfitting although the performance is lower than XGBoost and Random Forest.

![Image1](https://github.com/ThuyTran102/DS-Midterm-Project/blob/main/images/baseline_models_comparison.png)

- Tried reducing features that have low correlation with the target variable but did not yield better performance result.
- After hyperparameter tuning for XGBoost, Random Forest, Linear Regression, although the model's performance did not increase significantly, XGboost is still the winner.

![Image2](https://github.com/ThuyTran102/DS-Midterm-Project/blob/main/images/tuned_XGBoost.png)

![Image3](https://github.com/ThuyTran102/DS-Midterm-Project/blob/main/images/tuned_XGBoost_graph.png)


## Challenges 
- Insufficient, poor diverse data may have led to learning limitation: the model may have fail to learn more general and important patterns. The model is too complex compared to the amount of data, resulting in overfitting to the training data and performing poorly on new data.
- The baseline models did not explained variance in the target variable, Sale Price, very well (70%-80%).
- Feature engineering for year built into property age and latitude & longitude into location interaction did not improve model performance.
- Hyperparameter tuning long time with a lower yet significant increase.
- The manual Grid Search took a longer amount of time in avoidance to data leakage for **Median prices** based on city and state had to redone during each cross validation. 

## Future Goals
- Implementing some research about other features and data that might be useful to predict housing prices.
- Enhancing the model by incorporating additional data sources or more advanced algorithms.
- Exploratory data analysis from this project has potential to provide visuals to prospective Builders and Home buyers to gather data about current and past house sale prices scenario.
