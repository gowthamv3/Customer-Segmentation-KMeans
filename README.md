# Customer Segmentation using K-Means Clustering
Customer segmentation project using K-Means Clustering with the Elbow Method and Silhouette Score to determine the optimal number of customer clusters and analyze customer profiles.

## Project Overview

This project demonstrates an unsupervised machine learning approach for **Customer Segmentation** using the K-Means Clustering algorithm.

The project uses the **Elbow Method** and **Silhouette Score** to evaluate different numbers of clusters and identify a suitable value of K.

After selecting the number of clusters, K-Means is applied to segment customers and analyze the characteristics of each cluster.

## Objective

The main objective of this project is to:

- Segment customers into meaningful groups.
- Determine a suitable number of clusters.
- Use K-Means Clustering for customer segmentation.
- Analyze the characteristics of each customer cluster.

## Dataset

The project uses the `customer_segmentation.csv` dataset.

The original dataset contains customer-related information such as:

- ID
- Gender
- Ever Married
- Age
- Graduated
- Profession
- Work Experience
- Spending Score
- Family Size
- Var_1
- Segmentation

For clustering, the notebook removes the non-numeric and irrelevant columns and uses the remaining numerical features.

## Data Preprocessing

The following preprocessing steps are performed:

1. Load the dataset using Pandas.
2. Remove irrelevant and categorical columns.
3. Remove rows containing missing values.
4. Standardize the numerical features using `StandardScaler`.

The following columns are removed before clustering:

- `ID`
- `Gender`
- `Ever_Married`
- `Graduated`
- `Profession`
- `Spending_Score`
- `Var_1`
- `Segmentation`

## Machine Learning Algorithm

### K-Means Clustering

K-Means is an unsupervised machine learning algorithm that groups similar observations into clusters.

The notebook tests different values of K from **2 to 10**.

```python
K_range = range(2, 11)
