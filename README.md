## Neural Network Model Report

## Overview

The purpose of this project was to develop a model using deep learning techniques such as neural networks to forecast the success rate of applicants and determine which to be funded by Alphabet Soup Charity. 

## Results

**The libraries used were:**
- Pandas
- sklearn.preprocessing - StandardScaler
- sklearn.model_selection - train_test_split
- TensorFlow

**Data Pre-processing:**
- A Pandas DataFrame was used to read the data of a csv file, charity_data.csv from static.bc-edx.com.
  
- The columns EIN and NAME were dropped in Model 1 and Model 2 as they were neither targets nor features.
  
- Target Variable (y) 
  - IS_SUCCESSFUL. This represents the applicant's success status. 
    
- Features (x)
  - APPLICATION_TYPE
  - AFFILIATION
  - CLASSIFICATION
  - USE_CASE
  - ORGANIZATION
  - STATUS
  - INCOME_AMT
  - SPECIAL_CONSIDERATION
  - ASK_AMT
    
- Binned and cutoff low value-counts of application_types (app_count < 500) classifications (class_count < 1000)

- Data was converted to numeric using get_dummies and transformed with train_test_split and StandardScaler for training and test sets.
    
**Compiling, Training, and Evaluating the Model:**

The Keras Library, deep learning model, was used for model 1 with len(X_train[0]) was used for the shape of the model and 2 hidden layers with 80 and 30 neurons. the relu activation function was selected for the hidden layers while the sigmoid activation function was selected for the output layer (with one neuron). The 'adam' optimizer was utilized with a binary cross-entropy loss function. This model obtained an accuracy of 72.57%.

For model 2, the similar approach was conducted. However, to optimize model 1 and improve it's accuracy, the following modifications were completed:
- Added another hidden layer
- Adjusted the # of neurons in each hidden layer with 132 in the first layer, 88 in the second, and 44 in the third.
- Changed the activation functions for the hidden layers to tanh.
- Decreased random_states from 78 to 42.

This achieved an accuracy of 72.49%

## Summary

The target accuracy to achieve was 75%. Neither model 1 (72.57%) nor the optimized model 2 (72.49%) achieved this goal. In fact, even with adding another hidden layer and more neurons in each layer, and even using a different activation function the accuracy did not increase performance. The shaping of the model in the preprocessing steps are critical in attempting to improve performance. As this dataset incurred a classification problem, a different machine learning model may be considered such as Random Forest or one that depends on Logistic Regression as we only want to see if the organization is successful or not. 
