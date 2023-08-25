# Tanzanian Water Wells

<p align="center">
  <img width="400" height="300" src="images/well_hands.png">
</p>

## Overview
This project uses data on various water wells in Tanzania and attempts to build a predictive model to discern between operational and non-operational water wells. The data contains information on each water well, such as longitude, latitude, funder, management, pump type, and much more. The Tanzanian government can use this analysis and predictive model to decide where to allocate funding for water wells.

## Business Understanding

<p align="center">
  <img width="300" height="200" src="images/Screenshot 2023-08-25 at 12.15.00 PM.png">
</p>

Tanzania is a developing country with a population of over 57 million people. This country struggles to provide its large population with clean water. However, there are many water wells throughout the country. The Tanzanian government needs a way to predict if these water wells are operational or non-operational. Due to the nature of this problem, predicting a water well is operational when in reality it is not is more costly than predicting a water well is non-operational when in reality it is.

## The Data

The [data](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/23/) we used comes from [Taarifa](https://taarifa.org/). Taarifa is an open-source platform for crowdsourced reporting of infrastructure-related issues. This data consists of a surplus of information on the wells, including location, pump type, water quality, who manages the well, who funded the well, and much more.

## Data Preparation

The data contained a ternary classification problem by nature. The target column had three unique values:
  1. Functional
  2. Functional needs repairs
  3. Non-functional

This was turned into a binary classification problem by grouping ‘Functional’ and ‘Functional needs repairs’ into one group labeled ‘Operational’. Then, ‘Non-functional’ was relabeled to ‘Non-operational’.

There were a lot of null values within this dataset. In order to keep the majority of the data, an imputation process was implemented. Specifically, the MissForest imputer was used. This machine-learning process uses decision trees and random forests to predict missing values. This is one of the best ways to impute nulls and keep the data distribution intact.

## Modeling - Logistic Regression

The first model we evaluated was a Logistic Regression model. Using [GridSearch](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html), we were able to optimize the hyperparameters of the model. Seeing as our goal was to minimize the occurrence of 'false positives - non-operational well labeled as operational - we focused on the precision score metric. Our logistic regression model was 73% precise when predicting the condition of water wells in Tanzania. 

<p align="center">
  <img width="400" height="300" src="images/Screenshot 2023-08-25 at 10.19.48 AM.png">
</p>


As this Logistic Regression model was only 73% precise, we ran a Decision Tree model and compared results.

## Modeling - Decision Tree

## Conclusion - Final Model Evaluation

## Next Steps

1. **Inferential Modeling**: We would like to dive deeper into the feature importance of our data to see which variables had the largest effect on whether or not a water well is operational.

2. **Where and how new wells should be built**: We would also like to design a model to predict where, geographically speaking, to build new wells and how to build them. Specifically, what type of equipment to use when installing the new wells.

3. **Pull more recent data**: The most recent data in the data set we used was over ten years old. We want to use more recent data to make our analysis more relevant.

## Repository Structure

```
├── Data
├── Dev_Notebooks
├── images
├── .gitignore
├── LICENSE
├── README.md
└── notebook.ipynb
```
