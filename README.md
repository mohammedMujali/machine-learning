# README – ARTI308 Lab5 (Gym Members Version)

## Notebook Name
`ARTI308 Lab5 - Gym Members.ipynb`

## Overview
This notebook is a **classification lab** focused on **feature engineering** using the `gym_members_exercise_tracking.csv` dataset.

The original notebook was based on an order-status prediction dataset. It was adapted so the same workflow is now applied to a **gym members exercise dataset**.

In this version, the notebook predicts **`Workout_Type`** using member, body, hydration, heart-rate, and exercise-session features.

---

## Dataset Used
`gym_members_exercise_tracking.csv`

The dataset includes information such as:
- Age
- Gender
- Weight and Height
- BMI
- Fat Percentage
- Session Duration
- Calories Burned
- Water Intake
- Heart Rate values
- Workout Type

---

## Lab Goal
The purpose of this notebook is to:
- load and inspect the gym dataset
- confirm dataset quality
- define a classification target
- create meaningful engineered features
- prepare the data for machine learning
- train a classification model
- evaluate model performance
- interpret feature importance

---

## Notebook Structure

### 1. Setup and imports
The notebook imports the main libraries used for data analysis, preprocessing, visualization, and machine learning, including:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

### 2. Load the dataset
The notebook loads `gym_members_exercise_tracking.csv` into a pandas DataFrame.

### 3. Quick dataset checks
This section checks:
- dataset shape
- missing values
- duplicate rows

This helps confirm whether the dataset is clean before feature engineering starts.

### 4. Target variable and class balance
The classification target is:
- `Workout_Type`

This section shows how many records belong to each class and visualizes the distribution.

### 5. Identify feature types
The notebook checks data types to separate:
- numerical columns
- categorical columns

This is important for preprocessing and encoding.

### 6. Leakage awareness
This section explains that features used for prediction should be available at prediction time.

### 7. Feature engineering
This is the main part of the notebook. It creates new gym-specific features such as:
- `hr_range`
- `intensity_ratio`
- `recovery_gap`
- `calories_per_hour`
- `water_per_hour`
- `bmi_fat_interaction`
- `BMI_Category`
- `duration_band`

These features are designed to help the model better distinguish workout types.

### 8. Discretization (binning)
Some continuous variables are grouped into categories to improve interpretability and possibly model learning.

### 9. Prepare features for modeling
This section builds:
- `X` = input features
- `y` = target variable (`Workout_Type`)

It also removes columns that should not be used directly.

### 10. Train-test split
The data is split into training and testing sets using stratified sampling so class distribution remains balanced.

### 11. Encoding and baseline model
Categorical features are transformed using **One-Hot Encoding**.

A **Random Forest Classifier** is used as the baseline model.

### 12. Train and evaluate
The notebook evaluates the model using:
- accuracy
- classification report
- confusion matrix

### 13. Feature importance
This section shows which features contributed the most to predicting `Workout_Type`.

### 14. Optional feature selection
The notebook also includes an optional step using `SelectFromModel` to test whether a smaller subset of features can still perform well.

### 15. Student tasks
The final section includes tasks such as:
- creating a new engineered feature
- testing alternative feature rules
- discussing the effect of different preprocessing choices

---

## Main Engineered Features Explained

### `hr_range`
Difference between maximum heart rate and resting heart rate.

### `intensity_ratio`
A relative measure of exercise intensity based on heart-rate values.

### `recovery_gap`
Shows the difference between workout heart rate behavior and baseline heart-rate values.

### `calories_per_hour`
Calories burned divided by session duration.

### `water_per_hour`
Water intake divided by session duration.

### `bmi_fat_interaction`
A combined body-composition feature using BMI and fat percentage.

### `BMI_Category`
BMI transformed into categories such as underweight, normal, overweight, or obese.

### `duration_band`
Session duration grouped into bands such as short, medium, or long.

---

## Required Libraries
Install the required libraries before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

If you are using Jupyter Notebook, you can also run:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## How to Run
1. Put the notebook and `gym_members_exercise_tracking.csv` in the same folder.
2. Open the notebook in Jupyter or VS Code.
3. Make sure the correct Python environment is selected.
4. Run the cells from top to bottom.

---

## Common Error
### Error:
`ModuleNotFoundError: No module named 'pandas'`

### Fix:
Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

Then restart the kernel and run the notebook again.

---

## Notes
- This notebook keeps the **same lab steps and structure** as the original classification notebook.
- Only the dataset and domain-specific features were changed from food-order prediction to gym-member workout prediction.
- The machine learning workflow remains the same.

---

## Output
By the end of this notebook, you should be able to:
- understand feature engineering for classification
- train a baseline model on gym data
- evaluate prediction performance
- explain which features matter most

