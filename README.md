# salary_predictions_linear_regression
A machine learning project exploring salary prediction using Linear Regression and Scikit-learn.

# Salary Prediction Using Linear Regression

## Overview

The goal of this project is to build a machine learning model that predicts employee salaries based on several features, including age, gender, education level, job title, and years of experience.

The project follows a complete Linear Regression workflow, starting with data exploration and preprocessing, followed by model training, prediction, and evaluation.

## Dataset

The dataset used in this project is the **Salary Prediction Dataset**, obtained from Kaggle.

- **Dataset Creator:** Kiatttisak Rattanaporn
- **Source:** [Salary Prediction Dataset – Kaggle](https://www.kaggle.com/datasets/rkiattisak/salaly-prediction-for-beginer)
- **License:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

The dataset contains employee information and salary records.

### Features

- Age
- Gender
- Education Level
- Job Title
- Years of Experience

### Target Variable

- Salary

The original dataset contains 375 records. After removing rows with missing values, 373 records remain.

## Project Workflow

### 1. Data Loading and Exploration

- Loaded the dataset using Pandas.
- Inspected the dataset structure, dimensions, and data types.
- Generated statistical summaries.
- Checked for missing values.
- Explored the distribution of job titles.
- Visualized relationships between salary and numerical features.
- Compared average salaries across education levels.

### 2. Data Preprocessing

The following preprocessing techniques were applied:

- **Missing Values:** Removed rows containing missing values.
- **Gender Encoding:** Converted categorical gender values into numerical values using mapping.
- **Education Level Encoding:** Applied Ordinal Encoding to represent education levels numerically.
- **Job Title Encoding:** Applied One-Hot Encoding to convert job titles into numerical features.

### 3. Train-Test Split

The dataset was divided into training and testing sets:

- 80% Training Data
- 20% Testing Data

A fixed random state was used to ensure reproducibility.

### 4. Feature Scaling

Applied `StandardScaler` to standardize the input features.

The scaler was fitted on the training data and then used to transform both the training and testing sets to prevent data leakage.

### 5. Model Training and Prediction

A Linear Regression model from Scikit-learn was trained using the processed training data.

The trained model was then used to predict salaries for the testing set.

### 6. Model Evaluation

The model was evaluated using three regression metrics:

- **Mean Absolute Error (MAE):** Measures the average absolute difference between actual and predicted salaries.
- **Mean Squared Error (MSE):** Measures the average squared prediction error, giving greater weight to larger errors.
- **Root Mean Squared Error (RMSE):** Represents the prediction error in the original target units while penalizing larger errors.

An Actual vs. Predicted Salary plot was also generated to visually examine the model's predictions.

### 7. Baseline Model Comparison

A baseline model was created using Scikit-learn's `DummyRegressor` with the `mean` strategy.

This model predicts the average salary from the training set for every test employee, without considering individual features.

Its performance was compared with Linear Regression to determine whether using the input features improves salary predictions.

## Results

The following results were obtained on the test set:

| Evaluation Metric | Baseline Model | Linear Regression |
|---|---:|---:|
| MAE | 40,220.36 | 11,741.27 |
| MSE | 2,402,638,180.71 | 355,158,140.20 |
| RMSE | 49,016.71 | 18,845.64 |

### Results Interpretation

Linear Regression achieved lower error values across all three evaluation metrics compared with the baseline model.

This indicates that the selected features provide useful information for predicting employee salaries.

However, the results do not necessarily indicate that the model is optimal. Further investigation of prediction errors, dataset quality, and alternative regression algorithms could help improve performance.

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Google Colab
