# 02 - Logistic Regression Assignment

## Dataset Used

This assignment uses the **advertising.csv** dataset.

The dataset is used to build a Logistic Regression model that predicts whether a user clicked on an advertisement based on user information and advertising-related features.

## Files Needed

Make sure these files are in the same folder:

- `02-Logistic Regression Assignment.ipynb`
- `advertising.csv`

## Project Goal

The goal of this notebook is to apply Logistic Regression to an advertising dataset and predict the target column:

- `Clicked on Ad`

This is a binary classification problem:

- `1` = user clicked on the ad
- `0` = user did not click on the ad

## Main Steps in the Notebook

1. Import required libraries
2. Load the `advertising.csv` dataset
3. Explore the dataset using basic EDA
4. Check columns, missing values, and data types
5. Prepare the feature variables and target variable
6. Split the data into training and testing sets
7. Train a Logistic Regression model
8. Make predictions
9. Evaluate the model using:
   - Confusion Matrix
   - Classification Report
   - Accuracy Score

## Target Variable

The target column is:

```python
Clicked on Ad
```

## Model Used

The notebook uses:

```python
LogisticRegression
```

from `sklearn.linear_model`.

## How to Run

1. Open the notebook in Jupyter Notebook or Google Colab.
2. Upload or place `advertising.csv` in the same directory.
3. Run each cell from top to bottom.
4. Review the final model evaluation results.

## Notes

This README is for the **advertising dataset version**, not the gym dataset version.
