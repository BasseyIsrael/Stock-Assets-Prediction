# Stock Portfolio Optimization
  This repository provides a platform for the predicting of future stock prices based on historical stock prices, and an optimization of a stock portfolio. Time series analysis is extensively explored in this project.


Random Forest, XG Boost and Linear regression seems to work very well on such a long data as well. We have taken around 12-15 years of historical data which was divided into Training, Validation and Testing. 

These algorithms are able to catch the trend and move close to the Actual closing price in the right direction with a very low Mean Absolute error(MAE). The Evaluation Metrics is above to see how each algorithm performed on each stock. They worked so well because of the Feature Extraction we did to extract around 60 features including lagged Index funds prices, Technical Indicators like Exponential Moving Average, RSI, ADR, Willam's R, bollinger bands and many more. 

LSTMs did not perform well on this as expected, as the data is not using any sequence of previous many time steps. and LSTM will work better on time series data once we provide it with previous 30-60 days of lookback data for every prediction. 
Thats what we will be doing in the next Notebooks and then we will move to Portfolio Optimization. 