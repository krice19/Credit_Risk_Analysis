# Credit_Risk_Analysis

## Overview

This analysis will look at data from 2019 that can potentially effect credit risk.  The goal is to test multiple machine learning algorithms to see how well high risk loans can be identified.  Credit risk is unbalanced in their data, since there are more good learns and risk loans.  Therefore, I will be using different techniques to train and evalute models to help the imbalanced data.  I will be testing two oversampling techniques, RandomOverSample and SMOTE, the undersampling technique ClusterCentroids, and the combination technique SMOTEENN.  Additionaly, I will test two other machine learning models that reduce bias, which are the BalanacedRandomForestClassifier and the Easy Ensemble AdaBoost Classifier.  After testing these 6 models, I will evaluate their performance. 
<br/>
Before training the data, I cleaned and preprocessed the dataframe to be used in the evaluation.  I did this by converting string types into numerical data, so sklearn can accurately process the data.  I also dropped any columns in the dataframe that only had 1 unique value in the entire column.  I droppde these columns becausee one unique value will not help us learn what affects credit risk. After training the preprocessed data, I scaled the data using StandardScaler.  This was a necessary step to ensure my data is on the same class during this analysis. After scaling the data, I proceeded with my 6 techniques. 

## Results

Accurary, precision, and recall scores are three different way to validate a classification model.  Accurary scores simply describes the percentage of predictions the model got right.   A high accruary score may not always mean a model is better than another.  This is because a model can accruately predict low risk loanns better than they can predict high risk loans.  If that were the case, we would not validate that accruary scoree because we want our model to correctly assess high risk loans.  A precision score can be described as out all that were predicted postive, what is the rate they are actually positive.  A recall score can be described as out of all of those that should be positive, what is the rate in which ones were actually identified as positive.   Below are pictures of the resulting accurary, precision, recall values from the six techniques:
<br/>

### Random Oversampling
![random_oversamp](/Images/random_oversamp.png)

### SMOTE Oversampling
![smote](/Images/smote.png)

### Cluster Centroids Undersampling
![cc_undersamp](/Images/cc_undersamp.png)

### Combination SMOTEENN
![combo_samp](/Images/combo_samp.png)

### Random Forest Classifier
![forest](/Images/forest.png)

### AdaBoost Classifier 
![adaboost](/Images/adaboost.png)

## Summary

A low precision value for high risk would mean that out of all predicted high risk, only a small amount correct predicted as high risk.  I would say a low precision score should not completely invalidate a model.  A company would rather predict high risk loans that were not risky instead of classifiying high risk as low risk.  On the other hand, a low recall score means that out of all loans that are actually high risk, only a few were correctly identified as high risk.  While all factors can help evalute the models, I would say we should look for models with higher recall scores because a low score could cause a company to give out risky loans without realizing.  The Random Forest Classifier and AdaBoost Classifier have low recall scores, less than .40.  The two oversampling and one undersampling techniques have pretty high recall scores, but very low precision scores.  While all the techniques are not perfect, my recommendation would be to use the random or smote oversampling techniques with caution.  They have high accruary and recall scores, but low precision for high risk. This means a good amount of the high risk loans were correctly identified as high risk, but the methods may be overcompensating with classifying low risk credit risk as high risk due to the low recall rate. 