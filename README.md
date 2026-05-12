# Credit Card Customer Segmentation using K-Means

## Project Overview

This project applies **K-Means Clustering** to segment credit card customers based on their financial behavior. The goal is to group customers with similar spending, payment, and credit usage patterns so that businesses can better understand different customer profiles.

The analysis was completed in the notebook:

`02-Credit Card Customer Segmentation Assignment_Completed_Executed.ipynb`

## Dataset

The dataset used in this project is:

`CC_GENERAL.csv`

It contains credit card customer information such as balance, purchases, cash advance, credit limit, payments, and tenure.

## Main Objectives

The main objectives of this assignment are:

- Load and explore the credit card customer dataset.
- Clean the data and handle missing values.
- Remove unnecessary columns such as customer ID.
- Visualize customer behavior using plots.
- Scale the dataset before clustering.
- Apply the K-Means clustering algorithm.
- Use the Elbow Method and Silhouette Score to help choose a suitable number of clusters.
- Analyze the characteristics of each customer segment.
- Visualize the clusters using PCA.

## Tools and Libraries Used

The following Python libraries were used:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Project Steps

### 1. Import Libraries

Required Python libraries were imported for data handling, visualization, preprocessing, clustering, and evaluation.

### 2. Load the Dataset

The dataset `CC_GENERAL.csv` was loaded using pandas.

### 3. Data Exploration

The dataset was explored by checking:

- First rows of the data
- Dataset shape
- Column names
- Data types
- Summary statistics
- Missing values

### 4. Data Cleaning

The `CUST_ID` column was removed because it is only an identifier and does not help with clustering.

Missing values were handled using appropriate statistical methods, such as filling missing numeric values with the median.

### 5. Data Visualization

Several visualizations were created to understand the dataset, including:

- Histograms
- Correlation heatmap
- Scatter plots

These visualizations helped identify patterns and relationships between customer features.

### 6. Feature Scaling

The dataset was scaled using `StandardScaler` because K-Means is distance-based and is affected by feature scale.

### 7. K-Means Clustering

K-Means clustering was applied to group customers into clusters based on similar behavior.

### 8. Choosing the Number of Clusters

Two methods were used to evaluate the number of clusters:

- Elbow Method
- Silhouette Score

These methods helped select a reasonable number of clusters for customer segmentation.

### 9. Cluster Analysis

After clustering, the cluster labels were added to the dataset. The average values of features were then compared across clusters to understand each customer group.

### 10. PCA Visualization

Principal Component Analysis was used to reduce the dataset into two dimensions so the clusters could be visualized clearly.

## Expected Output

The notebook produces:

- Cleaned dataset
- Data visualizations
- Elbow Method plot
- Silhouette Score results
- Cluster labels for customers
- Cluster summary table
- PCA cluster visualization
- Final interpretation of customer segments

## How to Run the Notebook

1. Open the notebook file:

   `02-Credit Card Customer Segmentation Assignment_Completed_Executed.ipynb`

2. Make sure the dataset file is in the same folder:

   `CC_GENERAL.csv`

3. Run all cells from top to bottom.

4. Review the graphs, clustering results, and final answers.

## Conclusion

This project demonstrates how unsupervised machine learning can be used to segment credit card customers. K-Means clustering helps identify different customer groups based on financial behavior, which can support marketing strategies, customer management, and business decision-making.

