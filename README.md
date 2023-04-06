
# Prediction of Optimum supply quantity

## Problem Statement
A FMCG brand which entered instant noodles business two years back is facing inventory cost loss due to mismatch in demand and supply.
The higher management wants to build a model predicting the optimum supply for the warehouses to prevent the loss 


## Description of Dataset
The access to the brand's supply chain dataset was limited..The given dataset has 25000 rows and 24 variables.The dataset has variables of integer,float and Object datatypes.Dataset has missing values.The dataset has information about the warehouses such as warehouseID,Size,location,Certification status,Flood impact,Power backup,the number of retail shops in the warehouse region and few other variables as predictor variables.Here the Target variable is "prod_wg_ton".

### 1.EDA
### Dataset info
Total No. of Predictor variables =23,
Target Variable = "prod_wg_ton"

### 2.Descriptive Summary
Pandas describe() can provide a quick summary of the data set as outlined in the notebook.  The output of pandas describe(include="all") is shown below. Here, all columns of the DataFrame are included in the analysis.

### From this summary we can say that
#### 1.The average no. of refillings in last 3 months  for each ware house = 4.08
#### 2.The average no. of distributors for each ware house = 42.4
#### 3.The average no. of breakdowns  in last 3 months  for each ware house = 3.48
#### 4.The average no. of times storage issue reported  in last 3 months/ware house = 17.13

### No. of Missing values
#### workers_num = 990 
#### wh_est_year = 11881
#### app_wh_govt_certificate = 908

### 3.Variable analysis
The variables are plotted in different plots to carryout univariate ,Bi-variate and Multi-variate analysis.The distribution of the variables are studied using Histogram.The Boxplots are used to detect the outliers.The correlation between the variables are studied using pairplot and correlation plot.

### 4.Data Cleaning and Preprocessing
#### Missing value Treatment
The missing values in "workers_num" is treated with Median.
KNN imputation is used for imputing values in "Wh_age_years"
#### Outlier Treatment 
The outliers are treated with lower and upper whisker values.

### 5.Data Transformation
#### One hot encoding
Variables - Location_type,zone,wh_regional_zone,wh_owner_type
#### Label encoding
Variables - app_wh_govt_certificate,wh_capacity_size

### 6.Data Split
The  Dataset is split into train and test set in the ratio of 70:30

### 7.Clustering
The dataset is split into 2 clusters by using k-means clustering. The number of clusters is chosen by using Wss plot.

### 8.Data Transformation
The Data transformation is done using Standard Scaler method.The transformation is done as a pre-requisite for models such as ANN.

### 9.Model Building
The prediction models are built using 
#### 1.Linear Regression
#### 2.Decision tree
#### 3.Random Forest regressor
#### 4.Artificial Neural Network

### 10.Model Evaluation and Hyper Parameter Tuning
The performance of models are compared in both Train and test set.The models are further tuned using Hyper parameter tuning(Grid search cv)
The models are evaluated using various performance measures such as  RMSE (Train and Test), MAPE (Train and Test) and Accuracy of the models.
The Random Forest Regressor is chosen as best model with accuracy of 99.37%.
