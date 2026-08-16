# House Price Prediction

## Overview

This project uses machine learning to predict residential house prices using the Ames Housing dataset from Kaggle.

The project explores the relationship between housing characteristics and sale prices, followed by the development and comparison of several regression models.

## Dataset

The dataset contains 1,460 residential properties in Ames, Iowa, with 79 explanatory variables describing features such as:

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

1. Data loading and exploration
2. Exploratory data analysis
3. Missing-value analysis
4. Feature preprocessing
5. Feature encoding
6. Train/test split
7. Linear Regression
8. Random Forest Regression
9. XGBoost Regression
10. Hyperparameter tuning
11. Model comparison
12. Feature importance analysis

## Exploratory Data Analysis

The analysis found that several variables had strong relationships with house prices.

The strongest numerical correlations with `SalePrice` included:

- OverallQual
- GrLivArea
- GarageCars
- GarageArea
- TotalBsmtSF
- 1stFlrSF

The relationship between Overall Quality and Sale Price was also visualised.

## Models

Three machine learning models were evaluated:

| Model | RMSE | R² |
|---|---:|---:|
| Linear Regression | 29,395 | 0.887 |
| Random Forest | 29,003 | 0.890 |
| XGBoost | 25,713 | 0.914 |
| Tuned XGBoost | 25,028 | 0.918 |

## Results

XGBoost performed best among the models tested.

After hyperparameter tuning, the XGBoost model achieved:

- RMSE: 25,028
- R²: 0.918

The results show that gradient boosting was able to capture nonlinear relationships between property characteristics and sale prices more effectively than the baseline linear model.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- Jupyter Notebook
- Kaggle

## Future Improvements

Possible improvements include:

- More extensive feature engineering
- Cross-validation
- Additional ensemble models
- More systematic hyperparameter optimisation
- Prediction on the Kaggle test dataset