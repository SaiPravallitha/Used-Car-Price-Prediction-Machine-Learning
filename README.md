# Predicting Used Cars Prices
## Machine Learning Project
## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Model Inferences](#model-inferences)
- [Conclusion](#conclusion)
- [Recommendation](#recommendation)

### Project Overview
The project involved predicting used car prices through machine learning, utilizing data cleaning, feature engineering, and model exploration, ultimately selecting Random Forest for its high accuracy and low Mean Absolute Error, providing insights for optimizing used car inventory and pricing strategies.
The motivation behind this project arises from the inherent complexity of pricing used vehicles. The value of a used car is influenced by a myriad of factors, making it a challenging task for both sellers and buyers to determine a fair price. Car dealerships and online marketplaces can benefit from accurate price predictions to optimize their inventory. By ensuring the right mix of vehicles at prices aligned with market demand, businesses can maximize profitability and competitive advantage. Sellers can also utilize predicted prices to develop effective pricing strategies, attracting potential buyers while optimizing revenue.

### Data Sources
Vehicles Data: The primary dataset used for this analysis is vehicles.csv, obtained from Kaggle. The dataset used for this project is a robust collection of used vehicle listings from Craigslist within the United States. 

### Tools
- Excel
  - [Download here](https://microsoft.com)
- Jupyter Notebook
  - [Download here](https://www.anaconda.com/)

### Data Cleaning and Preprocessing

#### Actions Taken:
1. Reviewed and dropped irrelevant columns 
2. Removed duplicate entries
3. Handled missing values: Dropped rows with any missing data
4. Descriptive Statistics:
    - Executed statistical analysis on numerical features
    - Focus on percentiles: 0.01, 0.25, 0.5, 0.75, 0.99
    - Insights into central tendency, spread, and distribution characteristics
  
### Exploratory Data Analysis
EDA involved exploring vehicles data to answer key questions
#### Outlier Removal:
- Method Used: 
  - Interquartile Range (IQR) method
- Outcome: 
  - Removed outliers in 'price' and 'odometer' columns
- Unraveled distributions and correlations within the dataset
#### Feature Engineering
- New Features Created
- Transformations like One-hot encoding applied to categorical variables
- Feature Importance Evaluation

### Model Inferences
- LINEAR REGRESSION
   - From the R2 value obtained, it can be seen that the LR model was able to explain 71% of the variance in price.
   - However, considering that a significant portion (at least 75%) of the cars in the dataset are priced below $20,000, a mean absolute error of $4,403 is very high.
- POLYNOMIAL REGRESSION
   - Hyperparameter tuning up to 3rd degree and 5-fold cross-validation. 
   - There was no change in the R2 and mean absolute error values, as the optimal hyperparameter was still 1 based on the model performance score in the validation dataset.
- LASSO REGRESSION
   - Hyperparameter tuning ranging from 0.001 to 10. The optimal value based on validation set performance was 0.01.
   - However, there was no improvement in the R-Score value over the Linear Regression model.
- RIDGE REGRESSION
   - Hyperparameter tuning with alpha values ranging from 0.001 to 100. The optimal value based on validation set performance was 0.01.
   - However, there was no improvement in the R-Score value over the Linear Regression model.
- KNN
   - The hyperparameter ranged from 3 to 10, and the optimal value based on validation set performance was five neighbors. 
   - There was a slight improvement in the R2 value; it was 0.77 now against the 0.72 obtained from linear regression. However, the test mean absolute error was still very
     high at $3,400.
- DECISION TREE
   - Decision Tree was built by tuning the max_depth from 1 to 8, and the min_samples_split from 20 to 200 with an increase of 10 each time. The optimal parameters were depth=7, samples split = 40. 
   - The test R2 value obtained from this model was 0.78. Even though the test R2 value was slightly better than KNN, the mean absolute error was still high at $3718.
- RANDOM FOREST
  - Tried using Random Forest Regression with 100 trees and max_features set to 0.33. 
  - The results obtained from this model were the best up until now, with a test R2 value of 92% and a mean absolute error of $1,829. 
- ADABOOST ALGORITHM
  - Used a decision tree model with 100 estimators, a max_depth of 10, and a learning rate of 0.1. 
  - The test R2 value obtained from this model was 0.85, but the mean absolute error was very high at $3118.


### Conclusion
After deploying many models like Linear,Polynomial,LASSO-ridge,KNN and Random forest,\
Random Forest was chosen as the preferred model for drawing accurate price predictions with the R2 value of 91% and the lowest Mean Absolute Error which indicates effectiveness in providing results closest to real values.

### Recommendation
In the future, try experimenting with the parameters associated with Random Forest Regression can reduce overfitting


