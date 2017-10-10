# House-Price-Prediction---Boruta-Analysis
Kaggle House Price Prediction using Boruta Analysis

Data Exploration
Data Cleaning
Feature Selection
Data Preprocessing
Regression Modelling
Model Analysis & Comparison using RMSE
			1. Median Imputation
			2. Center & Scaling
			3. KNN


Major variables having NA’s:
Alley: Type of alley access to property.
PoolQC: Pool Quality.
Fence: Fence Quality.
MiscFeature: Miscellaneous features not covered in other categories.
Since it’s not important that every house has the above features, we can replace the NA’s with null because some of the Machine Learning Algorithms do accept NA’s.

Before starting with the data preprocessing we have to split the data into training & testing datasets.
Since we will be using the repeated Cross Validation method for training our model, we won’t be touching the test dataset and will convert the training data into smaller training and validation sets.
The training-validation ratio will be 0.8:0.2.
So we will be training our model in the training dataset and testing it on the validation data. Then for testing how well our model is doing, we will test it on the test dataset.

Data Preprocessing:
To tackle the remaining NA’s we use the Data Preprocessing functionality from the Caret package.
Caret package is a set of functions that attempt to streamline the process for creating predictive models.
We will use 3 methods for data preprocessing from the Caret package:
 Median Imputation
 Center & Scaling
 KNN

Train Control: Controls the computational nuances of the train function. 
Train: It is a CARET function to train the model. 

For this project, we will make a Linear Regression model and Random Forest for each of the data preprocessing methods like Median Imputation, Center & Scaling and KNN.

At the end of this process, we will have six models and then we can pick up the model with the least RMSE.
Linear Regression and Random Forest for three impuation methods.

Boruta Analysis:

Boruta Analysis is a feature selection process which is a part of the Boruta package.
It takes the predictor variables as input and returns their relative importance.
Internally, a copy is made of each input variable. These values are then permuted to remove any correlation with the target variable.
A Random Forest is then fitted to this entire dataset (original variables and their copies).
The Z-score is calculated and is divided by standard deviation to obtain variable importance. Higher Z-score leads to higher importance.

Conclusion:

From the analysis, we found that feature selection is important technique especially when there are lot of predictors. This improves our predicting power of the model. We also found that numerical NAs should not be neglected since it makes the model worse with poor prediction. So, proper preprocessing must be taken before modelling.
