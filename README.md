### Cryptocurrencies
Cryptos analysis using unsupervised machine learning and Python

## Overview

The purpose of this project is to analyze a dataset from many alternative cryptocurrencies to spot trends that help a firm or person figure out which are the best to invest in. The problem with cryptos is that the most common ones, like bitcoin or ethereum, are becoming unaffordable for the common public. During this analysis we will be using unsupervised machine learning to see if we can spot any trends that result in opportunities of these other Cryptocurrencies.

## Results

We did the preprocessing of the DataFrame to obtain a a DataFrame that could be used for Unsupervised Machine LearningThe following steps were performed on the crypto_df DataFrame:
- Removed all cryptocurrencies that are not being traded
- Removed all the rows that have at least one null value 
- Droped all columns that contain strings
- A new DataFrame was created that contains all cryptocurrency names, by adding the CoinName Column once more and retained the index from the original dataframe
- The get_dummies() method was used to create variables for the text features, which were then stored in a new DataFrame, X 
- The features from the X DataFrame were been standardized using the StandardScaler fit_transform() function

Next preprocessing work done was the reduction of the dimensions of the X DataFrame to three principal components, then we place these components in a new DataFrame.
- We created the pcs_df DataFrame that includes the following three columns:
    - PC 1
    - PC 2 
    - PC 3


Using our knowledge of the K-means algorithm, we created an elbow curve using hvPlot and found that the best value for K is 4. Then, we ran the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

![elbow](/Resources/elbow.png)


To complete the analysis we created vizualizations of the distinct groups that correspond to the three principal components we created in Deliverable 2, then we created a table with all the currently tradable cryptocurrencies using the hvplot.table() function. 

The clusters are plotted using a 3D scatter plot

![3dplot](/Resources/3dplot.png)

A table with tradable cryptocurrencies was created using the hvplot.table() function 

![table](/Resources/table.png)

hvplot scatter plot was created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class"

![scatter](/Resources/scatter.png)

## Summary

The job of unsupervised machine learning is to discover patterns or groups of data when there is no known output. That being said, this analysis was successful at grouping cryptocurrencies into 4 groups. If we were to create a crypto investment portfolio we would need to further analyze the clusters. This is a good starting point where we can see that the most profitable and known cryptos are somewhat in the 2 groups that have less supply and mined coins in comparison to others. 
Other than the obvious two we can see how the others are bahaving and use this study to make a decision on which cryptocurrency would be the best to invest in.