# ShortTermStockPrediction

This code takes stock price data as csv files and works on the Adj Close column.
The general idea here is to use the past 19 days' data to predict the 20th day's price. For every 20-day window, the first 19 datapoints will be the "x" and the 20th datapoint will be the "y". RNN will help us find the correlation between "x" and "y". We introduce a local normalization scheme for each 20-day group. We can use the min and max of the first half points in the group to apply min-max normalization to the whole 20 points (the resulting values are not necessarily between 0 and 1). This is to reduce correlation introduced by the normalization process.Then, we will do the usual training-test splitting, modeling, training, and testing.
