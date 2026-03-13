# Data Quality Assessment & Preprocessing — Gym Members Dataset

This project is a corrected version of the original lab notebook. The notebook was updated to use the **Gym Members Exercise Tracking** dataset instead of the chocolate sales dataset.

## Files

- `4- Data Quality Assessment & Preprocessing - Gym Members.ipynb` — corrected Jupyter notebook
- `gym_members_exercise_tracking.csv` — dataset used by the notebook
- `Chocolate_Sales.csv` — original dataset file from the older version (not used in the corrected notebook)

## Project Overview

The notebook demonstrates common **data quality assessment** and **data preprocessing** steps used in machine learning workflows, including:

- loading a dataset
- checking data types
- converting suitable columns to categorical types
- identifying missing values
- handling missing data
- detecting outliers
- treating outliers
- feature scaling and normalization
- encoding categorical variables
- dimensionality reduction using PCA

The examples in this version are based on gym-related features such as:

- `Age`
- `Gender`
- `Workout_Type`
- `Session_Duration (hours)`
- `Calories_Burned`
- other numeric fitness attributes in the dataset

## Requirements

Install these Python packages before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

If you are using Jupyter Notebook, you can also run this inside a notebook cell:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

## How to Run

1. Make sure the notebook and `gym_members_exercise_tracking.csv` are in the same folder.
2. Open the notebook in **Jupyter Notebook** or **VS Code**.
3. Select a Python environment/kernel that has the required packages installed.
4. Run the cells from top to bottom.

## Fix for `ModuleNotFoundError: No module named 'pandas'`

If you get this error:

```python
ModuleNotFoundError: No module named 'pandas'
```

it means the current Python environment does not have the required libraries installed.

Use one of these commands:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

or:

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn
```

Then restart the kernel and run the notebook again.

## Notes

- The notebook was adjusted so it looks for the dataset in common locations, including the current folder and `/mnt/data/`.
- `Gender` and `Workout_Type` are treated as categorical features where appropriate.
- PCA is included as an example of dimensionality reduction after preprocessing the data.

## Author / Course Context

Prepared as a lab-style notebook for **Data Quality Assessment & Preprocessing** using a gym-members dataset.
