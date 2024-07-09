## Overview

This project aims to analyze and cluster cryptocurrencies based on their performance metrics using K-Means clustering and Principal Component Analysis (PCA). The project involves several key steps including data preprocessing, determining the optimal number of clusters, applying K-Means clustering, and visualizing the results.

## Table of Contents

- Overview
- Technologies Used
- Project Structure
- Methodology
  - Data Preprocessing
  - Finding the Best Value for k
  - Clustering with K-Means
  - Principal Component Analysis (PCA)
  - Optimizing Clusters with PCA
  - Visualization and Comparison
- Results
- Conclusion
- License


## Project Structure

- `crypto_clustering.ipynb`: Main Jupyter Notebook containing the analysis and clustering steps.
- `requirements.txt`: List of Python packages required to run the project.
- `crypto_market_data.csv`: Dataset containing the cryptocurrency performance metrics.
- `README.md`: This README file.

## Methodology

### Data Preprocessing

The initial dataset consists of various performance metrics for different cryptocurrencies. These metrics include:
- Price change percentage over 24 hours
- Price change percentage over 7 days
- Price change percentage over 14 days
- Price change percentage over 30 days
- Price change percentage over 60 days
- Price change percentage over 200 days
- Price change percentage over 1 year

The data is first scaled to ensure that all metrics contribute equally to the clustering process.

### Finding the Best Value for k

The elbow method is used to determine the optimal number of clusters (k) for the K-Means algorithm. This involves:
- Running the K-Means algorithm for k values ranging from 1 to 11.
- Plotting the inertia values to visually identify the "elbow point" which indicates the best value for k.

### Clustering with K-Means

Using the best value for k determined from the elbow method:
- Initialize and fit the K-Means model using the original data.
- Predict the clusters and add these predictions to the original dataset.
- Visualize the clusters using a scatter plot with `hvPlot`.

### Principal Component Analysis (PCA)

PCA is applied to reduce the dimensionality of the data:
- Create a PCA model with three principal components.
- Transform the original data using the PCA model.
- Calculate the explained variance to understand how much information is retained in the principal components.

### Optimizing Clusters with PCA

Repeat the clustering process using the PCA-transformed data:
- Determine the best value for k using the elbow method with the PCA data.
- Initialize and fit the K-Means model using the PCA data.
- Predict the clusters and add these predictions to the PCA-transformed dataset.
- Visualize the clusters using a scatter plot with `hvPlot`.

### Visualization and Comparison

Compare the results of the clustering analysis:
- Create composite plots to compare the elbow curves and cluster visualizations from the original and PCA data.
- Analyze the impact of using fewer features (PCA) on the clustering results.

## Results

- The best value for k is found to be 4 for both the original and PCA-transformed data.
- PCA helps in reducing noise and highlighting important features, resulting in more compact and well-defined clusters.

## Conclusion

This project demonstrates the effectiveness of using K-Means clustering combined with PCA for analyzing and clustering cryptocurrencies based on their performance metrics. The use of PCA not only reduces the dimensionality of the data but also enhances the quality of the clustering results.
