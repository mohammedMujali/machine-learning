# Support Vector Machines Assignment

## Project Overview

This project applies a **Support Vector Machine (SVM)** classifier to the famous **Iris flower dataset**. The goal is to classify iris flowers into one of three species based on their physical measurements.

The three flower species are:

- Setosa
- Versicolor
- Virginica

The dataset features are:

- Sepal length
- Sepal width
- Petal length
- Petal width

---

## Files Included

| File | Description |
|---|---|
| `02-SVM Assignment_Completed_Executed.ipynb` | Completed Jupyter Notebook with all required code, visualizations, model training, evaluation, and GridSearchCV tuning. |
| `README_SVM_Assignment.md` | Explanation of the project and how to run it. |

---

## Tools and Libraries Used

The notebook uses the following Python libraries:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

---

## Assignment Steps Completed

### 1. Load the Dataset

The Iris dataset was loaded using Seaborn:

```python
iris = sns.load_dataset('iris')
```

A fallback using `sklearn.datasets.load_iris()` was also included in case the Seaborn online dataset does not load.

---

### 2. Exploratory Data Analysis

A pairplot was created to visualize relationships between the features:

```python
sns.pairplot(iris, hue='species')
```

From the pairplot, **setosa** appears to be the most separable flower species because it forms a clearly separate cluster, especially when comparing petal length and petal width.

---

### 3. KDE Plot

A KDE plot was created for the **setosa** species using:

- Sepal width
- Sepal length

This visualization shows the density distribution of setosa flowers based on sepal measurements.

---

### 4. Train/Test Split

The dataset was divided into features and labels:

```python
X = iris.drop('species', axis=1)
y = iris['species']
```

Then it was split into training and testing sets:

```python
train_test_split(X, y, test_size=0.30, random_state=101)
```

---

### 5. SVM Model Training

An SVM classifier was created and trained:

```python
model = SVC()
model.fit(X_train, y_train)
```

---

### 6. Model Evaluation

The model was evaluated using:

- Confusion matrix
- Classification report

These metrics show how well the model predicted the flower species in the test set.

---

### 7. GridSearchCV Tuning

GridSearchCV was used to test different values for:

- `C`
- `gamma`
- `kernel`

The parameter grid used was:

```python
param_grid = {
    'C': [0.1, 1, 10, 100, 1000],
    'gamma': [1, 0.1, 0.01, 0.001, 0.0001],
    'kernel': ['rbf']
}
```

---

### 8. Final Model Evaluation

After tuning, predictions were created again using the best GridSearchCV model. A new confusion matrix and classification report were printed.

The SVM model performed very well. Since the Iris dataset is small and easy to classify, the improvement after GridSearchCV may be slight or may remain almost the same.

---

## How to Run the Notebook

1. Open the completed notebook in Jupyter Notebook, JupyterLab, or Google Colab.
2. Run all cells from top to bottom.
3. Review the generated plots and classification reports.

---

## Conclusion

This assignment demonstrates how to use a Support Vector Machine classifier for a multi-class classification problem. The Iris dataset was visualized, split into training and testing data, trained using SVM, evaluated using classification metrics, and tuned using GridSearchCV.

The most separable species was **setosa**, and the final SVM model achieved strong classification performance.

