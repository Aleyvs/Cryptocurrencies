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

![]("/Resources/elbow.png")


To complete the analysis we created vizualizations of the distinct groups that correspond to the three principal components we created in Deliverable 2, then we created a table with all the currently tradable cryptocurrencies using the hvplot.table() function. 

The clusters are plotted using a 3D scatter plot


A table with tradable cryptocurrencies was created using the hvplot.table() function 

hvplot scatter plot was created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class"


