# Tanzanian_Water_Wells

## Overview
This project uses data on various water wells in Tanzania and attempts to build a predictive model to discern between operational and non-operational water wells. The data contains information on each water well, such as longitude, latitude, funder, management, pump type, and much more. The Tanzanian government can use this analysis and predictive model to decide where to allocate funding for water wells.

## Business Understanding
Tanzania is a developing country with a population of over 57 million people. This country struggles to provide its large population with clean water. However, there are many water wells throughout the country. The Tanzanian government needs a way to predict if these water wells are operational or non-operational. Due to the nature of this problem, predicting a water well is operational when in reality it is not is more costly than predicting a water well is non-operational when in reality it is.

## The Data

## Data Preparation

## Modeling - Logistic Regression

The first model we evaluated was a Logistic Regression model. Using 'GridSearchCV', we were able to optimize the hyperparameters of the model. Seeing as our goal was to minimize the occurrence of 'false positives - non-operational well labeled as operational - we focused on the precision score metric. Our logistic regression model was 73% precise when predicting the condition of water wells in Tanzania. 

img: ROC Curve

Seeing as this Logistic Regression model was only 73% precise, we chose to run a Decision Tree model and compare results.

## Modeling - Decision Tree

## Conclusion - Final Model Evaluation

## Next Steps
