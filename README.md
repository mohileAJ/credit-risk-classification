# credit-risk-classification

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis: Use the classification approach to predict the creditworthiness of borrowers, classifying them as healthy or high-risk. 
* Explain what financial information the data was on, and what you needed to predict:  The "lending data" file contains financial information loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, etc.  These are to assess the borrower's ability to repay the loan that they are applying for.  The metrics are used for analysis of such credit risk profile of the borrowers.     
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).The summary of the dataset loaded from the dataframe provides baseline information on the loan_status (which will be the target variable), along which the predictions relating to the dataset will made, classifying the borrowers as healthy ('0') and high-risk ('1'). 
* Describe the stages of the machine learning process you went through as part of this analysis: a. Preprocess - Creating the labels for supervised learning, by separating the "loan-status" column (the target variable) from the rest of the dataset (i.e. the rest of the columns are the features or independent variables); and then splitting the dataset into training and testings datasets. b. Train - The target variables' labels of the training dataset are used to fit a model with the dataset of features. c. Validate - Use the model fitted by training data to validate on the testing dataset.  d. Predict - The testing features and the fitted model are used to make a prediction on the testing labels.  This machine learning process is then used to make predictions on labels for new data.  
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms). Logistics regression is a linear model based on the classification approach, and is used to make predictions (for new datapoints) that are binary (i.e. categorical) outcomes. It follows aforesaid machine learning stages of Preprocess, Train, Validate, and Predict. 

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Description of Model 1 Accuracy, Precision, and Recall scores.

- The model has a high accuracy rate <(TP + TN) / (TP + TN + FP + FN)> of 0.99 for both the dataset comprising of 19,384 datapoints (Healthy: 18,761; and High-Risk: 623).  
- The precision scores <(TP / (TP + FP))> for the Healthy borrowers are 1.00 while those for the High-Risk borrowers are 0.84. 
- The recall scores <(TP / (TP + FN))> for Healthy borrowers are 0.99, while those for the High-Risk are 0.91.      

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
The model's high accuracy rate of 0.99 for both the Healthy and High-Risk borrowers, may not provide an accurate metric for assessing the performance, considering the imbalance between the two label classes (given that there are more healthy loans, i.e. "true" cases, than high-risk loans in the dataset). 

The model's high precision rate of 100% for healthy loans suggests that there are no false-positive (i.e., the loans classified as healthy were all actually healthy).  With reference to the high-risk loans, the model predicted comparatively higher levels of false-positives (i.e., the loans classified as high-risk were not actually high-risk for 16% of the observations). 

The recall scores are upwards of 0.9 for both healthy and high-risk loans, although the levels of false-negatives were higher for the high-risk loans. In other words, of all the actual High-Risk borrowers, the model incorrectly classified such borrowers as Healthy for 9% of the cases.  This would adversely impact the credit quality of the portfolio. 


* Which one seems to perform best? How do you know it performs best?
Overall, the model certainly looks good, with excellent ability to identify Healthy borrowers, while the ability to classify the High-Risk borrowers could be improved by optimizing the model and adding more High-Risk cases to the dataset. 

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
True.  From the perspective of missed lending opportunities (i.e. predicting '1''s correctly), the model generates high precision as well as recall rates.   Weakness - However, there is a need to reduce the 16% of the false-positives in classifying high-risk loans; as well as the 1% of the times in classifying an healthy loan as high-risk. 

From the perspective of reducing the credit risk of the portfolio (i.e., predict '0''s correctly): Weakness - there are 9% cases of high-risk loans' predictions that are being classified as healthy borrowers. This could have an adverse impact if large amount of loans are extended to such High-Risk borrowers. 

If you do not recommend any of the models, please justify your reasoning: The above-mentioned model weaknesses could be mitigated by adding a filter such as manual credit review processes focused on the cusp of the Healthy and High-Risk borrowers' quallity / credit risk rating. In other words, credit processes along the set of the least Healthy borrowers and the best High-Risk borrowwers could use more focused review performed by credit risk experts.  
