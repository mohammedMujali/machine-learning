# README for `4- Data Quality Assessment & Preprocessing - Gym Members.ipynb`

This README is written **for the same notebook** and explains what each section in the notebook does.

## Notebook purpose
This notebook is a practical lab for **data quality assessment and preprocessing** using the dataset:

- `gym_members_exercise_tracking.csv`

The notebook shows how to:
- inspect data types
- convert suitable columns
- detect and handle missing values
- detect and handle outliers
- normalize data
- apply PCA

---

## Files used
Keep these files in the **same folder** when possible:

- `4- Data Quality Assessment & Preprocessing - Gym Members.ipynb`
- `gym_members_exercise_tracking.csv`

Optional images used in markdown cells:
- `step2.png`
- `Mean.png`
- `median_formula_2.png`
- `IQR.png`
- `percentile.png`
- `min_max.png`
- `zscore.png`

If the images are missing, the notebook code still works, but some markdown illustrations may not display.

---

## Libraries needed
Install these Python libraries before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

If you are using Jupyter, you can run this in a cell:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## If you get `ModuleNotFoundError: No module named 'pandas'`
This means the notebook kernel does not have the required package installed.

Use:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn
```

Then:
1. Restart the kernel
2. Run all cells again

---

## What each notebook section does

### 1) Import Libraries
The notebook imports:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

These are used for data handling and visualization.

---

### 2) Load Dataset
The notebook loads the gym dataset using a reliable path check.

It tries:
- `gym_members_exercise_tracking.csv`
- `/mnt/data/gym_members_exercise_tracking.csv`

This makes the notebook easier to run in different environments.

Main dataframe name:
- `df`

---

### 3) Data Quality Assessment
The notebook checks data types using:

```python
df.dtypes
```

It explains that:
- `Age` should be numeric
- `Calories_Burned` should be numeric
- `Gender` and `Workout_Type` are better as categorical values

Then it converts:
- `Gender` → `category`
- `Workout_Type` → `category`

This improves data organization and is useful for preprocessing.

---

### 4) Handling Missing Values
The notebook first checks whether the dataset already contains missing values:

```python
df.isna().sum()
```

Because the dataset may not contain enough missing values for practice, the notebook **creates artificial missing values** in:

- `Calories_Burned`

A copy of the dataframe is created:
- `df_missing`

Then the notebook demonstrates 3 ideas:

#### Strategy 1: Remove records
Uses:

```python
df_missing.dropna()
```

This is useful when only a small number of rows are missing.

#### Strategy 2: Mean imputation
Replaces missing `Calories_Burned` values with the mean.

New dataframe:
- `df_imputed_mean`

#### Strategy 3: Median imputation
Replaces missing `Calories_Burned` values with the median.

New dataframe:
- `df_imputed_median`

Median is usually safer when outliers exist.

---

### 5) Handling Outliers
The notebook studies outliers in:

- `Calories_Burned`

First, it shows a boxplot.
Then it uses the **IQR method**:

- `Q1`
- `Q3`
- `IQR`
- lower bound
- upper bound

Records outside the range are stored as outliers.

Then the notebook shows 2 handling methods:

#### Remove outliers
Creates:
- `df_no_outliers`

This removes rows outside the IQR limits.

#### Cap outliers
Creates:
- `df_capped`

This uses percentile capping:
- 5th percentile
- 95th percentile

So extreme values are clipped instead of deleted.

---

### 6) Data Transformation - Normalization
The notebook normalizes these numerical features:

- `Calories_Burned`
- `Session_Duration (hours)`

#### Min-Max Normalization
Uses:
- `MinMaxScaler`

New dataframe:
- `df_scaled`

This scales values to the range **0 to 1**.

#### Z-Score Standardization
Uses:
- `StandardScaler`

New dataframe:
- `df_standardized`

This transforms features so they are centered around 0 with standard deviation near 1.

---

### 7) Correlation Before PCA
Before PCA, the notebook checks correlation between:
- `Calories_Burned`
- `Session_Duration (hours)`

It uses a heatmap to show whether the features are related.

This helps explain why PCA may be useful.

---

### 8) PCA (Principal Component Analysis)
The notebook applies PCA to the standardized features:

- `Calories_Burned`
- `Session_Duration (hours)`

It uses:

```python
PCA(n_components=2)
```

Output stored in:
- `principal_components`

The notebook prints:
- explained variance ratio

Then it plots the PCA projection.

This shows how the original features can be represented in principal components.

---

### 9) Assignment section
At the end, the notebook includes an assignment asking the student to:
- identify data quality issues
- apply a missing value strategy
- detect and handle outliers
- normalize numerical features
- apply PCA and explain the result

---

## Important dataframe names used in the notebook
- `df` → original dataset
- `df_missing` → dataset after adding artificial missing values
- `df_removed` → rows with missing values removed
- `df_imputed_mean` → missing values filled with mean
- `df_imputed_median` → missing values filled with median
- `df_no_outliers` → dataset after removing outliers
- `df_capped` → dataset after capping outliers
- `df_scaled` → Min-Max normalized data
- `df_standardized` → Z-score standardized data
- `principal_components` → PCA output

---

## How to run the notebook correctly
1. Open the notebook in Jupyter or VS Code.
2. Make sure the Python kernel is selected correctly.
3. Install the required libraries.
4. Make sure `gym_members_exercise_tracking.csv` is available.
5. Run the notebook from top to bottom.

---

## Expected learning outcome
After finishing this notebook, the student should understand how to:
- inspect dataset quality
- choose suitable data types
- handle missing data
- detect outliers with IQR
- scale features correctly
- prepare data for machine learning
- reduce feature dimensions using PCA

---

## Note
This notebook is the **gym-members version** of the lab, not the chocolate-sales version.
All dataset-specific examples were adjusted to match the gym dataset.
