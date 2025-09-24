# 🏠 Zillow Housing Price Prediction

Predicting the **tax-assessed value** of residential properties using a cleaned Zillow dataset. The project explores key factors affecting home prices and builds regression models to estimate property values accurately.

## Project Overview

The project is divided into 2 main sections:

### Data Cleaning & EDA
- Handle missing values, remove irrelevant columns, and treat outliers.  
- Explore relationships between features and the target variable (`taxvaluedollarcnt`).  
- Visualize distributions and correlations to identify important predictors.

### Modeling & Feature Engineering
- Create new features to improve predictions.  
- Test three regression models:
  - Ridge Regression  
  - Lasso Regression  
  - Decision Tree Regressor  
- Tune hyperparameters and compare models using **RMSE** and **MAE**.  
- **Decision Tree Regressor** performed best and was selected as the final model.

## Goal
Understand the main drivers of property values and create an accurate predictive model.
