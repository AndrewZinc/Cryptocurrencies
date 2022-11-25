# Cryptocurrency Analysis with Unsupervised Machine Learning

## Overview of the Analysis
This analysis used unsupervised machine learning to determine the clustering within a large collection of cryptocurrencies. The major activities performed were:
* Preprocessing the data for PCA (Primary Component Analysis)
* Reducing data dimensions using PCA
* Clustering cryptocurrencies using KMeans
* Visualizing cryptocurrency results

## Technology
This project included the following technologies:
* Python - The programming language.
* Jupyter Notebook - The web-based interactive computing platform for developing the Python code and executing the analysis.
* crypto_data.csv - Input data file, courtesy of: (https://min-api.cryptocompare.com/data/all/coinlist)
* Scikit-Learn - Machine Learning tools for Python
* hvPlot - Open Source high-level API for data exploration and visualization.

## Analysis

The analyis operations were performed mainly on Pandas DataFrames and NumPy ndarrays.

### Data-cleansing

The initial DataFrame containing the imported CSV data was reviewed and cleaned to remove rows with untraded cryptocurrencies, null values, and to convert strings to numeric values. Selected columns were removed because they would not provide value in the subsequent operations.

### Data Scaling

StandardScaler was used to scale the cleansed dataframe, so there would be an equal basis for comparison of the relative importance of the data features.

### Data Dimension Reduction via PCA

PCA was performed to reduce the DataFrame data dimensions down to three components.

### Determination of the best value of "K", using the "Elbow Curve"

A for-loop performed 10 iterations and the computed values were plotted to reveal the "Elbow Curve".  Using this visualization, a value of 4 for "K" was selected to construct the cryptocurrency clusters.

### Scatter Plot of Four Clusters

A 3D Scatter plot was constructed using Plotly Express.  This diagram reveals that all of the clusters are distinct and discernable.

### Table of Tradeable Cryptocurrencies

An interactive (sortable/selectable) table was constructed using hvPlot, and populated with all of the tradeable cryptocurrency details.

### Scatter Plot of Tradeable Cryptocurrencies

A final DataFrame was constructed using scaled data for the TotalCoinSupply and TotalCoinsMined data, along with DataFrame (columns) from the prior cleansing and exploratory operations on this data. This DataFrame was used to construct an interactive hvPlot scatter plot.  The user is able to pan and zoom into areas of interest, and hover data is displayed for the points of interest.  The data point decorations change when a point is selected.