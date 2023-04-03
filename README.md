# deep-learning-challenge

## Overview of the Analysis

### Background
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

### Data Exploration 

The dataset does not suffer through rare-case and oversampling or other techniques is not needed. 

![image](https://user-images.githubusercontent.com/89043234/229328422-bfc8acc9-b0b6-4e80-978a-e6cc5392f95a.png)

0 - NOT SUCCESSFUL || 
1 - IS SUCCESSFUL

Based on PCA and visualization of the data, the pattern suggest that a non-linear method should be applied. 

![image](https://user-images.githubusercontent.com/89043234/229328472-3eed192c-6c05-4234-8e70-f1c38c66d14a.png)

### Data Transformation/Methodology  

1. The EIN and NAME columns were dropped

2. For columns that have more than 10 unique values, binning was used to categorize rare occurances. 

3. One-Hot-Encoding was used to transform categorical data. 

4. The train and test were split 80/20. 

5. The training and testing features were scaled with StandardScaler() from sklearn. 

6. Various feature selection methods were used (Correlation against Y, Removal of co-variant and/or low variance features) to determine variables. 

## Results

* Machine Learning Model 1: Control (No Feature Selection or HyperOptimization)

#### Data Preprocessing 
* Variable Target: **IS_SUCCESSFUL** - predicts whether the funded organization will be sucessful
* All Variables were inputted, except for rare cases which were binned. 
* EIN, and NAME were dropped 

#### Compiling, Training, & Evaluating the Model
* Neural Structure (31, 128, 128, 1) 
* No steps were taken to improve model performance as this model served as control
* This model was not able to achieve the 75% accuraccy. 

| precision | recall | f1-score | support |      |
|----------:|-------:|---------:|---------|------|
|         0 |   0.75 |     0.62 | 0.68    | 3207 |
|         1 |   0.71 |     0.82 | 0.76    | 3653 |
|  accuracy | 72.86% |          |         |      |



* Machine Learning Model 2: Logistic Regression (After Resampling)

| precision | recall | f1-score |
|----------:|-------:|---------:|
|         0 |   1.00 |     0.99 |
|         1 |   0.85 |     0.99 |
|  accuracy |   0.99 |    15508 |


## Summary

The logistic regression models overall are better at predicting healthy loans (0) relative to high-risk loan. This is expected due to the significant disparity between healthy and high-risk loans. However, the oversampled data still predicts healthy loans (0) relatively better than high-risk loan (1). As seenm, the recall has significantly improved for high-risk loans at a slight sacrifice of recall for healthy loans - and should be the recommended model to predict unseen data. 
