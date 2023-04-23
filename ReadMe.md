# Consumer Loyalty Prediction

## 1. Background

- Company Description: Company E is mainly responsible for online payment business, and takes credit card as its core financial product, and has issued more than 110 million credit cards so far.Moreover, the product of Company E is not only a payment portal, but also an "o2o" platform. Through the App, users can check various services such as local restaurants, hotels, movies, travel tickets, etc., and support online payment by credit card.

- Business Goal: EThe core purpose of using machine learning algorithm technology is to better recommend local merchant services for food, clothing, housing and transportation to users in the App, including display of popular restaurants, reminders of discounts, etc. Its fundamental purpose is to make more personalized recommendations for each user: Merchant Category Recommendation. However, it should be noted that the modeling goal is to predict the loyalty score of the user.

- Algorithm Goal: User Loyalty Score Prediction. Predicting the rating of each user is essentially a regression problem.

- Evaluation Metric: RMSE. Smaller the better.

  

## 2. Dataset

- Data Dictionary
- training set
- test set (without target)
- Merchant Data
- Credit Card Transaction: historical_transactions
- Credit Card Transaction: new_merchant_transactions



## 3. Data Preprocessing Method

#### Training and test set

- Data correctness check: unique ID
- Missing value
- Outliers  
- Regularity Consistency Analysis between two sets of data
  - univariate analysis
  - Multivariate Joint Distribution



#### Merchant Data

- Correctness check
- Discrete/continuous field labeling
- Discrete value
  - Missing Value Labeling for Discrete Variables :  .fillna(-1)
  - Discrete Variable Dictionary Encoding
- Continuous Variables
  - infinite value processing - largest explicit value



#### Credit Card Transaction

- Compare merchant datasets
- Continuous/Discrete Field Labeling
- Field type conversion / missing value filling



## 4. Feature Engineering

- feature creation
  - generic composite
  - business statistics
- data merge



## 5. Modeling

### 5.1 Random Forest

- Feature Selection:  
  - Pearson correlation 

- parameter tuning 
  - RandomizedSearchCV
  - GridSearchCV
- cross validation - 5-fold



### 5.2 LightGMB

- Feature Selection
  - LightGBM (wrapper)
- Parameter Tuning
  - TPE
- cross validation: 5 fold



### 5.3 XGBoosting

- Feature optimization 
  - NLP  
    - CountVectorizer 
    - TfidfVectorizer
- Parameter Tuning
  - Bayesian optimizer



### 5.4 Ensemble 

- Voting
  - average
  - weigted
- Stacking



## 6. Result Estimation

| models                  | Private Score | Public Score |
| ----------------------- | ------------- | ------------ |
| randomforest            | 3.65455       | 3.74969      |
| randomforest+validation | 3.65173       | 3.74954      |
| LightGBM                | 3.69723       | 3.80436      |
| LightGBM+validation     | 3.64403       | 3.73875      |
| XGBoost                 | 3.62832       | 3.72358      |
| Voting_avr              | 3.63650       | 3.73251      |
| Voting_wei              | 3.633307      | 3.72877      |
| Stacking                | 3.62798       | 3.72055      |