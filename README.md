<h1 align="center">
  <img src="Stock Banner.png" alt="Stock Prediction Banner" />
</h1>


<div align="center">

# **Stock Assets Prediction Project**

</div>

<div align="justify">

 This repository provides access to everything relating to my project on stock price analysis, and prediction. Use this readme file to understand the project and the results obtained. If you would like to collaborate on a time series related project, you can contact me on israelbssy@gmail.com.


Please, feel free to contribute to the codes any way you can. Comment any script you would like for me to provide. Cheers!



 
</div>


<div align="center">

![Python version](https://img.shields.io/badge/Python%20version-3.10%2B-lightgrey?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/BasseyIsrael/Stock-Assets-Prediction?style=for-the-badge)
![GitHub repo file count](https://img.shields.io/github/directory-file-count/BasseyIsrael/Stock-Assets-Prediction/src?label=NOTEBOOKS&style=for-the-badge)
![Type of ML](https://img.shields.io/badge/ML%20TYPE-TIME%20SERIES%20REGRESSION-red?style=for-the-badge)
![GitHub repo size](https://img.shields.io/github/repo-size/BasseyIsrael/Stock-Assets-Prediction?style=for-the-badge)
![License](https://img.shields.io/github/license/BasseyIsrael/Stock-Assets-Prediction?style=for-the-badge)

[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)

For the Badges [source](https://shields.io/)






# **Key findings: In considering the technical indicators as prediction features, the Relative Strength Index (RSI) gives very strong prediction support for Lagged prices**

</div>

## **Author(s)**

- [Israel Bassey](https://github.com/BasseyIsrael)

## **Table of Contents**

  - [Introduction & Business Problem](#introduction--business-problem)
  - [Source of Data](#source-of-data)
  - [Methods Applied](#methods-applied)
  - [Quick Glance at Key Results](#quick-glance-at-key-results)
  - [Lessons Learned and Recommendation](#lessons-learned-and-recommendation)
  - [Limitation and Improvement Opportunities](#limitations-and-improvement-opportunities)
  - [Explore Notebook](#explore-notebook)
  - [Contribution](#contribution)
  - [License](#license  )

<div align="Justify">


# **Introduction & Business problem**

In many financial spaces, stock analysis and forcasting takes precedence as investments opportunities grow exponentially. As this increases, developing efficient prediction means to correctly forecast future trends considering the unstable and unpredictable market becomes more and more crucial. 
The case of Algorithmic Trading is seen especially in this project, considering the potential catastrophy that can follow a relatively small miscomputation. For the sake of the high volatility and uncertainty that follows the market, this project was developed that employs extensive consideration of technical factors that affect stock prices and the use of time series forecasting for relatively more accurate predictions.

## Business Questions
- What technical indicator should we keep and eye on as a feature?
- Which algorithm should be considered in running subsequent forecasts?
- Can we have a universal, reusable workflow that can be used on any stock at any time?
- How can we obtain the next day closing price?


# **Source of Data**

The data used in this project was fetched from the [Alpha_Vantage API](https://www.alphavantage.co/) for stock data.

The API provides data on stocks, cryptocurrency, adn technical indicators. To use the API in your project, you can use the codeblock below. Also check out the documentation [here](https://www.alphavantage.co/documentation/)

```bash
from alpha_vantage.timeseries import TimeSeries

ALPHA_VANTAGE_API_KEY = 'Obtain_API_Key'
ts = TimeSeries(key= ALPHA_VANTAGE_API_KEY, output_format='pandas')
```

# **Methods Applied**

For this project, the aim is to predict the closing pricee of stocks. The project is divided into sections which include Feature Extraction and Prediction. A further project involving Stock Portfolio Optimization can be found in a separate repository [here](https://github.com/BasseyIsrael/Stock-Portfolio-Optimization). 

## Feature Extraction [(View)](https://github.com/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/A-%20Feature%20Extraction%20with%20Technical%20indicators.ipynb)

Prediction requires features and for this reason, extensive feature extraction was performed in this project using specific features including lagged prices from the in-situ data properties and use of technical indicators. The indicators give us information on the stock like when it's overbought, oversold, price trend strength, etc.

The technical Indicators used for this purpose are: 

- [Bollinger Bands](https://www.investopedia.com/terms/b/bollingerbands.asp)
- [Simple Moving Average (SMA)](https://www.investopedia.com/terms/s/sma.asp)
- [Exponential Moving Average](https://www.investopedia.com/terms/e/ema.asp)
- [Average True Range (ATR)](https://www.investopedia.com/terms/a/atr.asp)
- [Average Directional Index (ADX)](https://www.investopedia.com/terms/a/adx.asp)
- [Commodity Channel Index (CCI)](https://www.investopedia.com/terms/c/commoditychannelindex.asp)
- [Rate-of-change (ROC)](https://www.investopedia.com/terms/r/rateofchange.asp)
- [Relative Strength Index (RSI)](https://www.investopedia.com/terms/r/rsi.asp)
- [Williams %R](https://www.investopedia.com/terms/w/williamsr.asp)
- [Stochastic Oscillator %K](https://www.investopedia.com/terms/s/stochasticoscillator.asp)

To improve reusability of the code to perform your personal feature extraction and refactoring, a pipeline was developed which mimcked the workflow used in the initial feature extraction process. The pipeline can be accessed [here](https://github.com/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/B-%20Stock%20Prediction%20Feature%20Extraction%20Pipeline.ipynb)


## Predictive Analysis [(View)](https://github.com/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/C%20-%20Stock%20Prediction%20with%20XGBoost%2C%20LSTM%2C%20RForest%2C%20Linear%20Regression.ipynb)

To obtain the new closing prices of the stocks, predictive algorithms were used. With extraction performed, lagging effects and technical indicator information are used as input variables for predicting the required closing prices.
The algorithms used are:
- [Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
- [XGBoost](https://xgboost.readthedocs.io/en/stable/) 
- [Random Forests Regression](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)
- [Long-Short Term Memory (LSTM)](https://www.tensorflow.org/api_docs/python/tf/keras/layers/LSTM)


# **Quick Glance at Key Results**

A look into the features extracted can be obtained in [this spreadsheet](https://github.com/BasseyIsrael/Stock-Assets-Prediction/blob/main/Saved%20Features/NETFLIX.csv)

The features extracted were also accesses to obtain the feature importance. A plot of the feature importance is presented. The Relative Strength Index (RSI) was seen to have the highest effect on the features

Feature importance of Technical Indicators

<img src="Assets\feature importance of technical indicators.png" alt="Feature Importance" />


The prediction algorithms listed above were used on 6 stocks and the performance of the developed predictors was used to determine a suggested model to employ given the features extraxted. An object oriented pipeline for prediction to make it easier to reuse the algorithm. 

The prediction plots obtained from the algorithms used are also presentes. To obtain more information about the workflow, you can access [the notebook](https://github.com/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/C%20-%20Stock%20Prediction%20with%20XGBoost%2C%20LSTM%2C%20RForest%2C%20Linear%20Regression.ipynb).

Actuals vs Prediction for Linear Regression (Goldman Sachs Group Inc Stock)

<img src="Assets\linear regression actual vs predicted.png" alt="Actuals vs Prediction" />

Actuals vs Prediction XGBoost (Nike Inc Stock)

<img src="Assets\XGBoost actual vs predicted.png" alt="Actuals vs Prediction" />

Actuals vs Prediction for Random Forests Regression (Nike Inc Stock)

<img src="Assets\Random forests actual vs predicted.png" alt="Actuals vs Prediction" />

Actuals vs Prediction for LSTM (Goldman Sachs Group Inc Stock)

<img src="Assets\lstm prediction.png" alt="Actuals vs Prediction for LSTM" />


The LSTM model structure


| Layer (type)              | Output Shape            | Param #   |
|---------------            |--------------------     |---------- |
| lstm_3 (LSTM)             | (None, 70, 32)          | 4352      |
|lstm_4 (LSTM)              | (None, 32)              | 8320      |
| dense_2 (Dense)           | (None, 1)               |33         |  


Giving more insights on the performance, a table showing the average performance for different metrics across the 6 stocks is also presented. 

<img src="Assets\Performance Results.png" alt="Performance" />





- ***Based on these features, the final model to be considered first is the XGBoost***
- ***It is observed that it performes better than all the other models across all metrics, without considering the linear regression model***
- ***The linear regression model shows an overfit with the data, hence should not be considered in this case.***
- ***LSTM model did not perform well considering these features and should be checked. For this, the features extracted do not work well with a time-series algorithm like LSTM. To handle this, an extra feature extraction was performed to obtain logged data of closing prices for the previous 30 days.***

The work on improving the LSTM model gave better results than the results obtained from the initial features used. 

A new LSTM model network was obtained.

| Layer (type)              | Output Shape            | Param #   |
|---------------            |--------------------     |---------- |
| lstm_1 (LSTM)             | (None, 60, 50)          | 10400     |
|lstm_2 (LSTM)              | (None, 50)              | 20200     |
| dense_1 (Dense)           | (None, 1)               | 51        |  
|Total params: 30,651             |
|Trainable params: 30,651         |
|Non-trainable params: 0          |

The new prediction made is also presented

Actuals vs Prediction for LSTM (IBM Stock)

<img src="Assets\new lstm prediction.png" alt="Actuals vs Prediction for LSTM" />

Performance Metrics

| R2       | MAPE     | RMSE   | MAE   |
|--------  |-----     |------  |------ |
|0.87  |3.24     |0.84  |0.67 |



The regression algorithms are able to adopt the trend and move close to the Actual closing price in the right direction with a very low Mean Absolute error(MAE). The Evaluation Metrics is above to see how each algorithm performed on each stock. They conformed to the Feature Extraction done to extract around 60 features including lagged Index funds prices, Technical Indicators like Exponential Moving Average, RSI, ADR, Willam's R, bollinger bands and many more.

LSTMs did not perform well on this as expected, as the data is not using a long sequence of time steps. LSTM worked better on time series following  30-60 days of lookback data for every prediction. The improvement is observed through the drastic reduction of the MAE to **0.67** with a coefficient of determination on **0.87**. 

# **Lessons Learned and Recommendation**

- From the analysis, it was observed that a set of values stand-out as important features in the prediction of the closing price. The value with the highest impact on prediction being the Relative Strength Index (RSI). This is seei=mingly expected considering the volitality of the prices being considered. This is not to say that th eother features play no part in the prediction process, however in a case on further work an dre-application requiring dimensionality reduction, the items to be overlooked are equally presented. 
- The behaviour of conventional regression algorithms would differ from the behaviour of algorithms specially suited for an application type like time-series forecasting. It is thus necessary to set up relevant features to be considered for prediction when using a set of algorithms.

- Recommendation would be to ensure that the data applied to a pipeline conforms to the necessary, and corresponding Index fund during feature extraction and prediction to keep the relevance of the features and prevent under-performance.

# **Limitations and Improvement Opportunities**

- Development of an interface that gives the user(s) ease of access to prediction.
- Using the interface to help users train their own algorithms and work with fresh data.

# **Explore Notebook**

- [A- Feature Extraction with Technical indicators.ipynb](https://nbviewer.org/github/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/A-%20Feature%20Extraction%20with%20Technical%20indicators.ipynb)
- [B- Stock Prediction Feature Extraction Pipeline.ipynb](https://nbviewer.org/github/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/B-%20Stock%20Prediction%20Feature%20Extraction%20Pipeline.ipynb)
- [C - Stock Prediction with XGBoost, LSTM, RForest, Linear Regression](https://nbviewer.org/github/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/C%20-%20Stock%20Prediction%20with%20XGBoost%2C%20LSTM%2C%20RForest%2C%20Linear%20Regression.ipynb)
- [D - Stock Prediction with LSTM (IBM).ipynb](https://nbviewer.org/github/BasseyIsrael/Stock-Assets-Prediction/blob/main/src/D%20-%20Stock%20Prediction%20with%20LSTM%20%28IBM%29.ipynb)


# **Run Locally**

Initialize git

```bash
git init
```


Clone the project

```bash
git clone https://github.com/BasseyIsrael/Stock-Assets-Prediction.git
```

enter the project directory

```bash
cd Stock-Assets-Prediction
```

Install the dependencies nad libraries to run the package using the requirements file. (recommended)

```bash
pip install requirements.txt
```

List all the packages installed

```bash
pip list
```



## Contribution

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change or contribute.

# **License**

MIT License

Copyright (c) 2022 Israel Bassey

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Learn more about [MIT](https://choosealicense.com/licenses/mit/) license
