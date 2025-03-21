# CryptoClustering

This project focuses on using Python and unsupervised learning techniques to analyze cryptocurrency market data. The goal is to determine whether cryptocurrencies are affected by 24-hour or 7-day price changes.

---

### Solution
- [`Crypto_Clustering.ipynb`](https://github.com/Saurabh-Lakhanpal/crypto-clustering/blob/main/Crypto_Clustering.ipynb): Starter code for the project.
- [`crypto_market_data.csv`](https://github.com/Saurabh-Lakhanpal/crypto-clustering/blob/main/Resources/crypto_market_data.csv): Contains cryptocurrency market data.
  
---

## Instructions

### Step 1: Load Data
Load the `crypto_market_data.csv` file into a DataFrame. Perform summary statistics and data visualization to understand the dataset.

### Step 2: Data Preparation
1. Use `StandardScaler()` from `scikit-learn` to normalize the data.
2. Create a new DataFrame with the scaled data. Set the original `coin_id` index as the index of the new DataFrame.

### Step 3: Finding the Optimal `k`
Utilize the **Elbow Method** to identify the best number of clusters (`k`):
1. Generate inertia values for `k` ranging from 1 to 11.
2. Plot the Elbow curve and select the optimal `k`.

### Step 4: Cluster Cryptocurrencies
1. Initialize and fit the K-means model with the optimal `k`.
2. Predict clusters and add the cluster labels as a new column in the DataFrame.
3. Use `hvPlot` to create a scatter plot:
   - X-axis: `price_change_percentage_24h`
   - Y-axis: `price_change_percentage_7d`
   - Color points by cluster and add `coin_id` to the hover columns.

### Step 5: Principal Component Analysis
1. Apply PCA to reduce features to three principal components.
2. Create a new DataFrame with the PCA results and maintain the original `coin_id` index.
3. Determine the total explained variance of the PCA components.

### Step 6: Optimizing Clusters with PCA
1. Repeat the **Elbow Method** using the PCA DataFrame.
2. Compare results with the original scaled DataFrame.
3. Cluster the data using K-means on the PCA DataFrame and visualize results.

### Step 7: Comparison of Results
Use composite plots (`hvPlot` with `+` operator) to compare cluster analyses:
1. Elbow curve from the original and PCA DataFrame.
2. Clusters derived from both methods.

Answer the following:
- What is the impact of using fewer features for clustering?

---

## Resources
- [hvPlot Documentation](https://hvplot.holoviz.org)
- [scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Python Official Documentation](https://www.python.org/doc/)
