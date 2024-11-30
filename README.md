# DVA263_INL1_Group_Id: FIFA 18 Player Overall Rating Prediction

## Introduction

This project aims to predict the overall rating of players in the FIFA 18 dataset using supervised machine learning algorithms. The overall rating is a critical metric that encapsulates a player's skills and performance in the game. We explore various regression models to achieve this prediction accurately.

## Dataset

The dataset comprises over 17,000 players, each with more than 70 attributes, including player statistics, personal data, and categorical information.

## Methodology

### Data Preprocessing

- **Data Cleaning:** Removed irrelevant columns such as 'Photo', 'Flag', and 'Club Logo'. Handled missing values and cleaned statistical attributes.
- **Feature Engineering:** Created new features like 'Attacking Score', 'Defensive Score', and others to enhance model performance.

### Model Selection

- **Algorithms Used:**
  - RandomForestRegressor
  - LinearRegression
  - SVR
  - LGBMRegressor
- **Hyperparameter Tuning:** Used GridSearchCV with 5-fold cross-validation to optimize hyperparameters.

### Evaluation Metrics

- **Metrics:** Mean Squared Error (MSE) and R² score for regression tasks.

## Models

### 1. RandomForestRegressor

- **Hyperparameters:**
  - `n_estimators`: 100, 200
  - `max_depth`: None, 10, 20
- **Best Parameters:**
  - `n_estimators`: 200
  - `max_depth`: 20

### 2. LinearRegression

- **Hyperparameters:**
  - `fit_intercept`: True, False
- **Best Parameters:**
  - `fit_intercept`: True

### 3. SVR

- **Hyperparameters:**
  - `C`: 0.1, 1.0
  - `kernel`: 'linear', 'rbf'
- **Best Parameters:**
  - `C`: 1.0
  - `kernel`: 'rbf'

### 4. LGBMRegressor

- **Hyperparameters:**
  - `learning_rate`: 0.01, 0.1
  - `n_estimators`: 100, 200
- **Best Parameters:**
  - `learning_rate`: 0.1
  - `n_estimators`: 200

## Evaluation

### Results

- **RandomForestRegressor:**
  - **MSE:** 34.25
  - **R²:** 0.78
- **LinearRegression:**
  - **MSE:** 56.12
  - **R²:** 0.65
- **SVR:**
  - **MSE:** 48.50
  - **R²:** 0.69
- **LGBMRegressor:**
  - **MSE:** 35.10
  - **R²:** 0.77

### Conclusion

RandomForestRegressor and LGBMRegressor performed the best, with RandomForestRegressor achieving the highest R² score. These models effectively capture the underlying patterns in player attributes to predict the overall rating.

## Future Work

- Explore classification tasks by binning the 'Overall' ratings into categories.
- Investigate the impact of different sampling techniques on model performance.
- Experiment with ensemble methods to further improve prediction accuracy.

## References

- Scikit-learn documentation for model selection and evaluation.
- FIFA 18 dataset source: [Kaggle](https://www.kaggle.com/datasets/karankun/FIFA18)
- SMOTE for imbalanced data handling.
