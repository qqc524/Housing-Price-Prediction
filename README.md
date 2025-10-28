# 🏠 Zillow Housing Price Prediction

Predicting the **tax-assessed value** of residential properties using a cleaned Zillow dataset. The project explores key factors affecting home prices and builds regression models to estimate property values accurately.

## Dataset

The dataset comes from the **Zillow property data**, containing details about residential homes in California.  
After data cleaning (handled in a previous notebook), this project starts with a **cleaned dataset** of:

- **72,148 rows**  
- **33 features** (property details, geographic info, and quality indicators)

## Project Overview

### 1. Data Cleaning & EDA
- Handle missing values, remove irrelevant columns, and treat outliers.  
- Explore relationships between features and the target variable (`taxvaluedollarcnt`).  
- Visualize distributions and correlations to identify important predictors.

### 2. Modeling
Three regression models were chosen to:
  - Ridge Regression  
  - Lasso Regression  
  - Decision Tree Regressor

Used Repeated K-Fold Cross-Validation to compute MAE and standard deviation.

### 3. Feature Engineering
New features were created to capture relationships and reduce skew:

- log(calculatedfinishedsquarefeet)
- log(lotsizesquarefeet)
- bath_per_bed (bathrooms per bedroom)
- sqft_per_room (average room size)
- sqft_x_bath (interaction between total size and bathrooms)

Log transformations reduce the effect of extreme values.
Ratio and interaction features help models understand home layout and size relationships.

### 4. Feature Selection
- Ridge and Lasso: **Sequential Feature Selector** to pick top features.
- Decision Tree: selected **top 15 features by importance**.

### 5. Hyperparameter Tuning

  **Ridge Regression:**
    - GridSearchCV on alpha. Best alpha: 550

  **Lasso Regression:**
    - GridSearchCV on alpha. Best alpha: 540

  **Decision Tree Regressor:**
    - RandomizedSearchCV for multiple parameters.

Best parameters: max_depth=12, min_samples_split=2, min_samples_leaf=10, max_features=0.8


### 6. Model Evaluation

Performance was compared using:
- MAE (Mean Absolute Error)
- Standard deviation of MAE (to assess model stability)


## Final Model Performance

* Decision Tree Regressor was the most accurate model.

* Ridge and Lasso required careful scaling and feature selection.

* Engineered features improved all models, especially Decision Tree.
