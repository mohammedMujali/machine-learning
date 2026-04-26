# K Nearest Neighbors Project

This project is a K-Nearest Neighbors (KNN) classification assignment using a synthetic dataset. The goal is to build, evaluate, and tune a KNN classifier that predicts the `TARGET CLASS` column from a set of numeric features.

## Project Files

```text
.
├── 02-K Nearest Neighbors Assignment.ipynb
├── KNN_Project_Data(1)
└── README.md
```

> Note: The dataset is a CSV-formatted file even though it does not include a `.csv` extension.

## Dataset Overview

The dataset contains **1,000 rows** and **11 columns**:

- `XVPM`
- `GWYH`
- `TRAT`
- `TLLZ`
- `IGGA`
- `HYKR`
- `EDFS`
- `GUUB`
- `MGJM`
- `JHZC`
- `TARGET CLASS`

`TARGET CLASS` is the label the model tries to predict. The other columns are numeric input features.

## Project Objective

The notebook walks through a typical supervised machine learning workflow:

1. Import required Python libraries.
2. Load the KNN project dataset.
3. Explore the data using basic inspection and visualization.
4. Standardize the feature variables.
5. Split the dataset into training and testing sets.
6. Train a KNN classifier.
7. Evaluate the model with a confusion matrix and classification report.
8. Use the elbow method to choose a better value of `k`.
9. Retrain the model with the selected `k` value.

## Requirements

Install the required Python packages before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## How to Run

1. Clone or download this project folder.
2. Make sure the notebook and dataset are in the same directory.
3. Open the notebook:

```bash
jupyter notebook "02-K Nearest Neighbors Assignment.ipynb"
```

4. Run the notebook cells from top to bottom.

## Example Code Flow

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import classification_report, confusion_matrix
```

Load the dataset:

```python
df = pd.read_csv("KNN_Project_Data(1)")
```

Standardize the feature columns:

```python
scaler = StandardScaler()
scaler.fit(df.drop("TARGET CLASS", axis=1))
scaled_features = scaler.transform(df.drop("TARGET CLASS", axis=1))
```

Train and evaluate a KNN model:

```python
X_train, X_test, y_train, y_test = train_test_split(
    scaled_features,
    df["TARGET CLASS"],
    test_size=0.30,
    random_state=101
)

knn = KNeighborsClassifier(n_neighbors=1)
knn.fit(X_train, y_train)
pred = knn.predict(X_test)

print(confusion_matrix(y_test, pred))
print(classification_report(y_test, pred))
```

## Choosing the Best K Value

The elbow method can be used to compare error rates for different `k` values:

```python
error_rate = []

for i in range(1, 40):
    knn = KNeighborsClassifier(n_neighbors=i)
    knn.fit(X_train, y_train)
    pred_i = knn.predict(X_test)
    error_rate.append((pred_i != y_test).mean())
```

Then plot the error rate:

```python
plt.figure(figsize=(10, 6))
plt.plot(range(1, 40), error_rate, marker="o", markersize=8)
plt.title("Error Rate vs. K Value")
plt.xlabel("K")
plt.ylabel("Error Rate")
plt.show()
```

## Expected Outcome

By the end of the notebook, you should have:

- A trained KNN classification model.
- Model evaluation metrics using a confusion matrix and classification report.
- An elbow plot showing how error rate changes across different `k` values.
- A final model retrained with a better selected `k` value.

## Notes

- Since KNN is distance-based, feature scaling is required before training.
- The dataset is artificial, so the column names do not represent real-world feature names.
- The final `k` value should be selected based on the elbow plot and model performance.
