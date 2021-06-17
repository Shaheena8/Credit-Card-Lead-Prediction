# Credit-Card-Lead-Prediction
Credit Card Lead Prediction 
Step 1: Understanding the Problem statement
First step is to identify a clear objective of what you want to do with data: a concrete question to answer, by observing the data set we can choose the correct category of algorithm (one among classification, regression or clustering) to be used to build the prediction model.
Imagine a black box with inputs as features and output as target variable. Then observe each variable there type where it is ordinal, nominal or integer.
 Step 2: Explore and Clean the Data (Exploratory data analysis):
Encoding categorical variable:
1.	In this dataset most of them are categorical variable of type nominal hence encoding of all the categorical features has to be encoded.
2.	Among them Region_Code and Channel_Code are encoded by checking there             probability of occurrences. Only 7 high probability (P > 0. 3) Region_Codes are considered   for analysis. Channel code also encoded in the same manner (only 3 levels we considered). 
3.	Encoded all other categorical variable with 2 levels, whereas all the levels in               Occupation feature is considered for analysis as they have direct effect on target variable.
Check for unbalanced data in the features:
Unbalanced data can be discovered by calculating the total unique values in each        categorical variable.
Checking for Null values:
1.	Check for Nan:
 Among the variables only one feature is having Nan values both   in training  and test dataset. Therefore I have used random forest imputation  algorithm to replace the  Nan values in the feature (Credit_Product) to get better  accuracy.
2.	 Nan Imputation:
o	In the training dataset considered for imputation, the target and ID features are        dropped from the dataframe. The feature to impute the nan is considered as a target variable.
o	The training data is divided into two sets, with target (Credit_Product ) feature without any nan values and other set with all the nan values (using drop along column)
o	Random forest algorithm is applied on the training dataset by splitting the training dataset (without nan) into xtrain and ytrain and xtest and ytest. The model accuracy is tested on the y test data variable with the predicted values. I have achieved an accuracy of 68.8%.
o	Then this model is used to predict the nan values to the target                            (Credit_Product ) variable.
o	The predicted values are combined with final data frame by concatenating both the test ant train datasets.

Step 3: Final training dataset used for modelling
1	As the distribution of the target Is_Lead data is random I have considered Random forest classification algorithm for modelling.
2	In this method the training dataset is splited into train and test sets and final classifier is estimated.
3	The classification report is generated and observed to get a  f1 score of 86% and accuracy to be 77%
Step 4: Applying on test dataset to predict the target variable
1	Apply encoding similar to the one applied for the training dataset
2	Apply Random Forest imputation on the Credit_Product feature
3	Apply the finalised classification model built on the training data set to estimate the target values.
4	Save the predicted output variable in csv file as per submission requirements. 


