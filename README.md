# Decision Trees and Random Forest Project

This project uses LendingClub loan data to predict whether a borrower will **not fully pay back** their loan. The analysis is completed in the Jupyter notebook:

`02-Decision_Trees_and_Random_Forest_Project_SOLVED.ipynb`

## Files

- `02-Decision_Trees_and_Random_Forest_Project_SOLVED.ipynb` — completed project notebook with code, visualizations, model training, and evaluation.
- `loan_data.csv` — dataset used by the notebook.
- `README_Decision_Trees_Random_Forest.md` — this README file.

## Project Goal

The goal is to build classification models that predict the `not.fully.paid` column:

- `0` means the borrower fully paid back the loan.
- `1` means the borrower did not fully pay back the loan.

## Dataset Columns

The dataset includes borrower and loan features such as:

- `credit.policy`
- `purpose`
- `int.rate`
- `installment`
- `log.annual.inc`
- `dti`
- `fico`
- `days.with.cr.line`
- `revol.bal`
- `revol.util`
- `inq.last.6mths`
- `delinq.2yrs`
- `pub.rec`
- `not.fully.paid`

## What the Notebook Does

1. Imports required Python libraries.
2. Loads `loan_data.csv` into a pandas DataFrame.
3. Explores the dataset using:
   - `info()`
   - `head()`
   - `describe()`
4. Creates exploratory visualizations:
   - FICO distributions by `credit.policy`
   - FICO distributions by `not.fully.paid`
   - Loan purpose countplot
   - FICO vs. interest rate jointplot
   - FICO vs. interest rate regression plots
5. Converts the categorical `purpose` column into dummy variables.
6. Splits the data into training and testing sets.
7. Trains a Decision Tree classifier.
8. Evaluates the Decision Tree with:
   - Classification report
   - Confusion matrix
9. Trains a Random Forest classifier.
10. Evaluates the Random Forest with:
    - Classification report
    - Confusion matrix
11. Compares model performance.

## Models Used

### Decision Tree Classifier

The Decision Tree model is trained using:

```python
DecisionTreeClassifier(random_state=101)
```

### Random Forest Classifier

The Random Forest model is trained using:

```python
RandomForestClassifier(n_estimators=600, random_state=101)
```

## Main Result

The Random Forest model achieves higher overall accuracy because it predicts the majority class, fully paid loans, very well.

However, the Decision Tree performs better at detecting the minority class, borrowers who did not fully pay back their loans, because it has higher recall for `not.fully.paid = 1`.

Because this dataset is imbalanced, accuracy alone is not enough. Recall and F1-score for the minority class are important when evaluating which model is more useful.

## How to Run

1. Place these files in the same folder:
   - `02-Decision_Trees_and_Random_Forest_Project_SOLVED.ipynb`
   - `loan_data.csv`

2. Open the notebook using Jupyter Notebook, JupyterLab, or VS Code.

3. Run all cells from top to bottom.

## Required Libraries

Install the required libraries with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

## Notes

- The notebook uses `random_state=101` so results are reproducible.
- The target class is imbalanced, so the Random Forest may look better by accuracy while still performing poorly on the minority class.
- A possible improvement would be to use class balancing, resampling, or model tuning.

