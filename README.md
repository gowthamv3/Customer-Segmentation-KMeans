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

Selecting the Number of Clusters

Two methods are used to evaluate the appropriate number of clusters.

1. Elbow Method

The Elbow Method evaluates the inertia, also known as the within-cluster sum of squares.

The value of K where the inertia curve shows an "elbow" can be considered a suitable number of clusters.

The notebook identifies:

Elbow K = 3
2. Silhouette Score

The Silhouette Score measures how well observations fit within their assigned clusters.

A higher Silhouette Score generally indicates better-defined clusters.

The notebook identifies:

Silhouette K = 4

The final implementation selects K based on the highest Silhouette Score.

Final K-Means Model

The final K-Means model uses the K value selected from the Silhouette Score:

final_K = K_range[np.argmax(silhouette_scores)]

The final model is then fitted to the standardized dataset.

final_model = KMeans(
    n_clusters=final_K,
    random_state=42,
    n_init=10
)
Cluster Analysis

After clustering, the project analyzes each cluster using:

Cluster Size
Average Age
Average Work Experience
Average Family Size

A cluster summary is created to understand the characteristics of each customer segment.

Visualization

The project includes visualizations for:

Elbow Method
Silhouette Score
Cluster Sizes
Average Cluster Characteristics
Intercluster Distances

Yellowbrick is also used for additional cluster visualization.

Technologies Used
Python
NumPy
Pandas
Matplotlib
Scikit-learn
Yellowbrick
Jupyter Notebook
Project Structure
Customer-Segmentation-KMeans/
│
├── Elbow Method & Silhouette Score for K selection - Customer Segmentation Dataset.ipynb
├── customer_segmentation.csv
└── README.md
How to Run the Project
1. Install Required Libraries
pip install numpy pandas matplotlib scikit-learn yellowbrick jupyter
2. Open Jupyter Notebook
jupyter notebook
3. Open the Notebook

Open:

Elbow Method & Silhouette Score for K selection - Customer Segmentation Dataset.ipynb

Make sure customer_segmentation.csv is in the same folder as the notebook.

4. Run the Notebook

Run the cells from top to bottom.

Conclusion

This project demonstrates how K-Means Clustering can be used to segment customers into different groups.

The Elbow Method and Silhouette Score are used to evaluate different values of K. The final clustering model is selected based on the highest Silhouette Score.

The resulting clusters are analyzed using customer characteristics such as Age, Work Experience, and Family Size.

Author

Gowtham V

License

This project is intended for educational and portfolio purposes.
