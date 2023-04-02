# deep-learning-challenge

## Overview of the Analysis

Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

In this deep learning model, the following features will be transformed, and selected, with a goal to achieve 75% accuracy.  

* **EIN and NAME**—Identification columns (Dropped)
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special considerations for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

The dataset suffers through a rare-case where the status of defaulted loans is signficantly lower than healthy loans. Resampling would later be used to address the problem in the results section. 

| loan_status | Frequency | 
|------------:|----------:|
|           0 |     75036 |  
|           1 |      2500 |  

0 - healthy loan || 
1 - defaulted loan 

Based on PCA and visualization of the data, the pattern suggest that a linear classification method (logistic regression) should be applied - followed by resampling. 

![image](https://user-images.githubusercontent.com/89043234/228358870-1075fd8c-2f9c-43e3-8cc8-c8e1749033e9.png)

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1: Logistic Regression (Before Resampling)

| precision | recall | f1-score |
|----------:|-------:|---------:|
|         0 |   1.00 |     1.00 |
|         1 |   0.86 |     0.91 |
|  accuracy |   0.99 |    15508 |

* Machine Learning Model 2: Logistic Regression (After Resampling)

| precision | recall | f1-score |
|----------:|-------:|---------:|
|         0 |   1.00 |     0.99 |
|         1 |   0.85 |     0.99 |
|  accuracy |   0.99 |    15508 |


## Summary

The logistic regression models overall are better at predicting healthy loans (0) relative to high-risk loan. This is expected due to the significant disparity between healthy and high-risk loans. However, the oversampled data still predicts healthy loans (0) relatively better than high-risk loan (1). As seenm, the recall has significantly improved for high-risk loans at a slight sacrifice of recall for healthy loans - and should be the recommended model to predict unseen data. 
