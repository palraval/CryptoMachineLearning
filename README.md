# CryptoMachineLearning


## Data Preprocessing 

The csv data file that contains crytocurrency market data is  normalized using the StandardScaler() function. This normalized data is saved as a DataFrame to be used for machine learning. 


## Clustering Crytocurrencies using Original Scaled Data 

An elbow curve is created by determining inertia values for various values of k. It was concluded that the k-value should be set to 4 due to it being the optimial cluster value before the inertia values started to plateau.

Using the optimal cluster value, a K-means model is constructed and fitted with the original scaled data. This model is then used to predict which cluster each of the crytocurrencies belong to and added to the DataFrame as a new column. A scatterplot is constructed with the x-axis containing the values within the "price_change_percentage_24h" column and the y-axis containing the values within the "price_change_percentage_7d" column of the DataFrame. Each of the points on the scatterplot are colored based on the respective cluster it belongs to to be able to visualize the clustering that the model predicted. 


## Clustering Crytocurrencies using Principal Component Analysis (PCA) 

PCA is performed on the original scaled DataFrame into three reduced components. The explained variance ratio is found and the total explained variance for the three components is calculated to be 0.895. The PCA data is converted to a DataFrame to be used for clustering. 

The optimal k-value for the PCA data is found through plotting the elbow curve. The elbow curve is created similarly to how it was done previously: the inertia values for various k-values was calculated and plotted as a line graph. The optimal k-value for PCA data was also found to be 4, just like with the original scaled data. 

Another k-means model is initialized using the optimal number of clusters (4). This model is fitted using the PCA data and is used to predict the clusters for this data. The predicted clusters is added as a new column to a copied DataFrame. With this copied DataFrame, a scatterplot is made with the x-axis being the "PCA1" column and the y-axis being the "PCA2" column. The data points on the scatterplot are colorized according to the cluster group that the model believes it belongs to. 


## Comparisons and Analysis

The elbow curves for the original scaled data and the PCA data are composited together for comparison purposes. By doing this, it can be concluded that the elbow curves look quite similar to one another. As already mentioned, the optimal k-value is the same for both. The inertia values for the PCA data are at a lower range than those for the original scaled data, indicating that there is better clustering for the PCA data. 

The scatterplots for the original scaled data and the PCA data are also composited together. The clustering after reducing the dimensionality does not show signs of negatively impacting the clustering. In fact, the clustering may actually be better after the PCA procedure due to the smaller inertia values.

