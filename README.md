# House Price Prediction

## Overview

This project uses machine learning to predict residential house prices using the Ames Housing dataset from Kaggle.

The project explores the relationships between housing characteristics and sale prices, followed by the development, comparison, and tuning of several regression models.

The main objective is to identify which machine learning approach provides the most accurate house price predictions.

## Dataset

The dataset contains 1,460 residential properties in Ames, Iowa, with 79 explanatory variables describing different characteristics of each property.

Examples of features include:

- Overall house quality
- Living area
- Garage capacity
- Basement area
- Number of bathrooms
- Year built
- Neighbourhood
- Property characteristics

The target variable is `SalePrice`.

## Project Workflow

The project follows these main steps:

1. Data loading and exploration
2. Exploratory data analysis
3. Missing-value analysis
4. Identification of numerical and categorical features
5. Data preprocessing
6. Categorical feature encoding
7. Train/test split
8. Linear Regression
9. Random Forest Regression
10. XGBoost Regression
11. Hyperparameter tuning using RandomizedSearchCV
12. Model comparison
13. Feature importance analysis
14. Actual vs predicted price analysis

## Exploratory Data Analysis

Missing values were investigated across the dataset, with several variables containing substantial numbers of missing observations.

The dataset was also examined to identify numerical and categorical features before preprocessing and model development.

Correlation analysis was performed to investigate relationships between numerical variables and `SalePrice`.

The strongest numerical correlations with `SalePrice` included:

- `OverallQual`
- `GrLivArea`
- `GarageCars`
- `GarageArea`
- `TotalBsmtSF`
- `1stFlrSF`
- `FullBath`
- `TotRmsAbvGrd`
- `YearBuilt`

A scatter plot was created to visualise the relationship between overall house quality and sale price.

## Visualisations

Several visualisations were created to explore the dataset and evaluate model performance.

### House Quality vs Sale Price

A scatter plot was used to examine the relationship between `OverallQual` and `SalePrice`.

The visualisation shows that houses with higher overall quality generally have higher sale prices.

### Model Performance

Model performance was compared using RMSE and R².

Actual vs predicted plots were also used to examine how closely the model predictions matched the actual sale prices.

Feature importance was analysed for the XGBoost model to identify the variables that contributed most strongly to predictions.

The saved visualisations can be found in the `images/` directory:

- `actual_vs_predicted.png`
- `feature_importance.png`
- `model_comparison_rmse.png`
- `model_performance_comparison.png`
- `tuned_xgboost_actual_vs_predicted.png`

## Models

Three regression models were initially evaluated:

| Model | RMSE | R² |
|---|---:|---:|
| Linear Regression | 29,395 | 0.887 |
| Random Forest | 29,003 | 0.890 |
| XGBoost | 25,713 | 0.914 |

XGBoost produced the best performance among the initial models.

## Hyperparameter Tuning

The XGBoost model was further optimised using `RandomizedSearchCV`.

The best parameters identified were:

```text
subsample = 0.7
n_estimators = 700
max_depth = 3
learning_rate = 0.05
colsample_by_tree = 1.0