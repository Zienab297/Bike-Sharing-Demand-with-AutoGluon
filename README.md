# Bike-Sharing-Demand-with-AutoGluon

This project develops a machine learning pipeline that classifies real-life disaster messages into multiple categories. It helps disaster response teams triage and route incoming messages more effectively by identifying the types of aid required or the nature of the message (e.g., request for food, medical help, infrastructure damage, etc.).

## Overview

Disaster situations generate a high volume of messages through social platforms and emergency systems. To assist emergency responders, this project automates the categorization of these messages into 36 predefined classes using Natural Language Processing (NLP) and supervised learning techniques.

The model can assign multiple categories to a single message (multi-label classification), allowing for comprehensive understanding and quicker action.



## Machine Learning Pipeline

This project used **AutoGluon** to automate model selection, preprocessing, and training. AutoGluon handled all feature engineering, model ensembling, and hyperparameter tuning.

- **Data Input**: Raw data from a disaster message dataset with labels.
- **Modeling**: AutoGluon's `TabularPredictor` was used to train a classification model.
- **Evaluation**: Model performance was assessed using **Mean Squared Error (MSE)** on the validation and test sets.

AutoGluon simplified the development process by managing data preprocessing, encoding, and model selection automatically.


- **Evaluation Metric**: 
  While AutoGluon evaluates classification metrics during training, this project additionally used **Mean Squared Error (MSE)** to compare predicted class indices with true labels. This helped provide a simple numeric measure of model accuracy post-inference.

## Model Evaluation

The model's performance was assessed using the Mean Squared Error (MSE), which measures the average squared difference between actual and predicted values across all output labels. MSE helped quantify the accuracy of the regression-based multi-label predictions.

|model|GBM|NN_TORCH|XGB|RF|score|
|--|--|--|--|--|--|
|initial|default|default|default|default|1.79717|
|add_features|default|default|default|default|0.60360|
|hpo|GBM Tuning|NN_TORCH Tuning|XGB Tuning|RF Tuning|0.60360|
