# ARTI308 Lab 6: Linear Regression with Gym Member Exercise Tracking

## Overview

This Lab 6 notebook has been updated from the original **USA Housing** dataset to use the **gym_members_exercise_tracking.csv** dataset.

The notebook builds a **Linear Regression** model to predict the number of calories burned by gym members based on exercise, body measurement, and workout-related features.

## Files Included

| File | Description |
|---|---|
| `ARTI308_Lab6_Gym_Corrected_Executed.ipynb` | Corrected and executed Jupyter Notebook for Lab 6 |
| `gym_members_exercise_tracking.csv` | Dataset used in the notebook |
| `README_Lab6_Gym.md` | Explanation of the project and how to run it |

## Dataset

The dataset contains information about gym members and their workout behavior.

Main columns include:

- `Age`
- `Gender`
- `Weight (kg)`
- `Height (m)`
- `Max_BPM`
- `Avg_BPM`
- `Resting_BPM`
- `Session_Duration (hours)`
- `Calories_Burned`
- `Workout_Type`
- `Fat_Percentage`
- `Water_Intake (liters)`
- `Workout_Frequency (days/week)`
- `Experience_Level`
- `BMI`

## Target Variable

The model predicts:

```text
Calories_Burned
```

## Features Used

The notebook uses the remaining columns as input features. Categorical columns such as `Gender` and `Workout_Type` are converted into numeric dummy variables using one-hot encoding.

## Main Steps in the Notebook

1. Import required libraries.
2. Load the gym dataset.
3. Explore the dataset using:
   - `head()`
   - `info()`
   - `describe()`
   - `columns`
4. Check for missing values and duplicate rows.
5. Visualize the data using:
   - Pair plots
   - Histograms
   - Correlation heatmap
   - Box plots
6. Prepare the data for machine learning.
7. Split the data into training and testing sets.
8. Train a Linear Regression model.
9. Generate predictions.
10. Evaluate the model using:
    - MAE
    - MSE
    - RMSE
    - R² Score

## Model Performance

The corrected notebook produced the following results:

| Metric | Value |
|---|---:|
| MAE | 31.1496 |
| MSE | 1719.7154 |
| RMSE | 41.4695 |
| R² Score | 0.9765 |

The high R² score shows that the model explains most of the variation in `Calories_Burned` for this dataset.

## Requirements

Install the following Python libraries before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

## How to Run

1. Place the notebook and CSV file in the same folder.
2. Open Jupyter Notebook or JupyterLab.
3. Open:

```text
ARTI308_Lab6_Gym_Corrected_Executed.ipynb
```

4. Run all cells from top to bottom.

## Important Note

The notebook expects the dataset file to be named exactly:

```text
gym_members_exercise_tracking.csv
```

If the file name is changed, update the `pd.read_csv()` line in the notebook.

## Summary

This corrected Lab 6 notebook successfully replaces the USA Housing regression task with a gym exercise tracking regression task. The final model predicts calories burned using gym member and workout information.
