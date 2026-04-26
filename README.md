# README - 02 Logistic Regression Assignment: Gym Dataset

## File
`02-Logistic_Regression_Assignment_All_Gym_Executed.ipynb`

## Dataset Used
`gym_members_exercise_tracking.csv`

This notebook was changed so the full assignment uses the gym members exercise tracking dataset instead of the original advertising or Titanic datasets.

## Main Goal
The notebook uses Logistic Regression to predict whether a workout session has a high calorie burn.

The target column created is:

`High_Calorie_Burn`

This target is based on the median value of `Calories_Burned`:

- `1` = calories burned is above the median
- `0` = calories burned is equal to or below the median

## Changes Made

- Loaded `gym_members_exercise_tracking.csv`
- Removed the old advertising/Titanic dataset workflow
- Created a binary classification target called `High_Calorie_Burn`
- Used `Calories_Burned` only to create the target, then removed it from the model inputs to avoid data leakage
- Split the data into training and testing sets
- Added preprocessing for:
  - numeric columns using `StandardScaler`
  - categorical columns using `OneHotEncoder`
- Built a `Pipeline` with preprocessing and `LogisticRegression`
- Trained the logistic regression model
- Generated predictions and prediction probabilities
- Evaluated the model using:
  - accuracy score
  - confusion matrix
  - classification report
- Added visualizations for gym data, including:
  - target distribution
  - workout type counts
  - high calorie burn rate by gender
  - high calorie burn rate by workout type
  - confusion matrix

## Libraries Required

The notebook uses:

```python
pandas
numpy
matplotlib
scikit-learn
```

## How to Run

1. Keep these two files in the same folder:
   - `02-Logistic_Regression_Assignment_All_Gym_Executed.ipynb`
   - `gym_members_exercise_tracking.csv`

2. Open the notebook in Jupyter Notebook, JupyterLab, Google Colab, or VS Code.

3. Run all cells from top to bottom.

## Important Columns

The model uses gym workout features such as:

- age
- gender
- weight
- height
- max BPM
- average BPM
- resting BPM
- session duration
- workout type
- fat percentage
- water intake
- workout frequency
- experience level
- BMI

The model does not directly use `Calories_Burned` as an input because it is used to create the target column.

## Final Output

At the end of the notebook, the model shows how well Logistic Regression predicts whether a workout belongs to the high calorie burn group or the low calorie burn group.
