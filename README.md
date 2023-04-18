# Alphabet Challenge 

## Overview of the Analysis

### Background/Purpose of Analysis 
Our objective is to predict the progression of PD in patients by analyzing their MDS-UPDRS scores. which measure progression in patients with PD. The Movement Disorder Society-Sponsored Revision of the Unified Parkinson’s Disease rating Scale (MDS-UPDRS) is a comprehensive assessment tool that measures both motor and non-motor symptoms associated with PD.

Our team developed models using data on protein and peptide levels over time in both individuals with PD, as well as in normal age-matched healthy controls. By doing so, we aim to uncover significant insights into the molecular changes that occur as PD advances, potentially leading to a groundbreaking discovery.

### Data Exploration 

![image](https://user-images.githubusercontent.com/89043234/232927072-8c42e49c-f731-4eab-99c7-618cf0b89607.png)

Based on box plot of the severity, there are outliers that can be explored in further detail. Due to time limitations, these outliers are not explored, but remains for future investigation. 

### Data Transformation/Methodology  




## Results

## Conclusion

Out of all three models, Model 3, with the inclusion of names may be the best in terms of metrics. However, further testing needs to be done to determine whether overfitting is an issue, and confirm if the addition of names is information leakage. Otherwise, Model 2 may be an alternative model. 

**Other Machine Learning Models**

Other Models such as Random Forest, XGBoost or other forms of ensemble learning should also be tested and compared against neural networks. These models have the benefit of being semi-white box models, explainable to stakeholders, have less-risk of overfitting, and also have the benefit of capturing non-linear relationships. 

## Appendix

[Figure Appendix]

![image](https://user-images.githubusercontent.com/89043234/229412083-faf2346b-776b-42e0-b511-f3783ccd6e2c.png)
