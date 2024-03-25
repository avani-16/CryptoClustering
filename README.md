# CryptoClustering

### Prepare the Data

- Used the 'StandadScaler()' module from 'scikit-learn' to normalize the data fromn the CSV file.
- Creatd a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### Find the Best Value for k Using the Original Scaled DataFrame
Used the elbow method to find the best value for k using the following steps:
 - a list with the number of k values from 1 to 11.
 - an empty list to store the inertia values.
 - a for loop to compute the inertia with each possible value of k.
 - a dictionary with the data to plot the elbow curve.
 - Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
   I found the best value for k is 4.

### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Used the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
 - Initialized the K-means model with the best value for k.
 - Fit the K-means model using the original scaled DataFrame.
 - Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
 - Created a copy of the original data and add a new column with the predicted clusters.
 - Created a scatter plot using hvPlot as follows:
      - Set the x-axis as "PC1" and the y-axis as "PC2".
      - Color the graph points with the labels found using K-means.
      - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Optimize Clusters with Principal Component Analysis
 - Using the original scaled DataFrame, performed a PCA and reduce the features to three principal components.
 - Retrieved the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
     - Retrieved the total explained variance of the three principal components to determine how much information can be attributed to each Principle Component.
     - Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### Find the Best Value for k Using the PCA Data
 - Used the elbow method on the PCA data to find the best value for k using the following steps:
     - Created a list with the number of k-values from 1 to 11.
     - Created an empty list to store the inertia values.
     - Created a for loop to compute the inertia with each possible value of k.
     - Created a dictionary with the data to plot the Elbow curve.
     - Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

       The best value for k using PCA data is still 4.

### Cluster Cryptocurrencies with K-means Using the PCA Data
Used the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
 - Initialized the K-means model with the best value for k.
 - Fit the K-means model using the PCA data.
 - Predicted the clusters to group the cryptocurrencies using the PCA data.
 - Created a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
 - Created a scatter plot using hvPlot as follows:
     - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
     - Color the graph points with the labels found using K-means.
     - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Observations
The impact of using PCA data resulted into tighter clusters, making it to distinguish between them than the original data. The PCA plot can also better isolate the two outliers, celsius-degree-token and ethlend. The results were accurate even with the missing data.


 
