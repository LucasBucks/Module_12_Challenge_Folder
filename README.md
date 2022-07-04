# Module_12_Challenge_Folder
Module 12 Challenge
# Module 12 Report Template

## Overview of the Analysis

The purpose of this analysis is to build a model that can help us better identify the creditworthiness of borrowers (those seeking a loan).  The basis of the model is built on current customer inputs that include loan size, interest rate, borrower income, debt to income, number of accounts, derogatory marks, total debt, and whether or not they were current on repaying the loan vs defaulting on the loan.  Taking this data, we want to predict if we can build a model that could help us find healthy borrowers in the future (folks who don't end up defaulting on the loan) and avoid high risk borrowers who would likely default on loan payments. We split the data up into two variables utilizing the customers current loan status as the benchmark.  If a client was current on a loan, the value we utilized was 0.  If they were in default, the value we used was 1.  This created 2 classes.  The majority class is 0 and the minority class is 1.  The data was imbalanced with 75036 loans current and only 2500 in default status.  In order to help imporve our model output, we ran a linear regression model utilizing the original data first and then ran the linear regression model with random oversized resampling to bring balance to our 0 and 1 (75036 for each).  Within the project, we started out reading the CSV file into jupyter lab.  Next we created our X and y variables to help us isolate the loan status column (y) and the rest of the features (X).  Next we needed to train the data with  "train_test_split" from scikit library.  Once that the data was trained, we fit it to the model with LogisticRegression, created our predictions, and evaluated the data.  It was important to implement the RandomOverSampling on the resampled data before running the LogisticRegression, creating a prediction, and evaluating the "balanced" data.  


## Results


* Machine Learning Model 1:
  * The logistic regression model scores high marks across the board regarding accuracy (95%), precision(100% for healthy and 85% for high-risk), recall (99% for healthy and 91% for high-risk), and f1 ratio (100% and 88% respectively) for both the majority sample size for healthy loans and minority sample size high risk loans.



* Machine Learning Model 2:
  * The linear Regression model scores high on accuracy (99%), high on precision (100% on healthy and 84% on high risk), high on recall (99% on both), and high on f1 (100% andd 91% respectively). It appears to do a good job of predicting both healthy loans and high-risk loans.

## Summary

* Which one seems to perform best? How do you know it performs best?  Based on the accuaracy scores, Model 2 performed the best (99% vs 95%).  Given the imbalanced data set, it's important to dig deeper than just the accuracy numbers.  With that in mind, Model 2 outperforms on recall as well whicch means it has a higher likely hood of predicting borrowers who would default.  They are about equal on precision of data.  All in all, both models perfromed well but model 2 has a slight advantage in predicting high risk borrowers which is ultimately what we want to avoid.  

