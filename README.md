# Advanced Intraday Trading Models

This is a capstone project, the 10th course of the Worldquant University.  
In this module, we will try to develop our own novelty strategy for **Intraday Trading Models**.  

<br>

## Object

This project aims to contribute to the field by introducing a unique and adaptive breakout trading model specifically crafted for the Indian stock market. This involves the following:
1. Leveraging advanced algorithms
2. Real-time data integration

<br>

## Methodology
1. Data collection
    - collected data ranging from 2024-02-20 to 2024-02-23 using the yfinance library in Python, and the data selection criteria are the top 30 stocks that make up the NESI Index in India. However, some stocks like MM.NS was delisted, so we collected available stocks' data in the below list.
```
"ADANIPORTS.NS", "ASIANPAINT.NS", "AXISBANK.NS", "BAJAJ-AUTO.NS", "BAJAJFINSV.NS",
"BAJFINANCE.NS", "BHARTIARTL.NS", "BPCL.NS", "BRITANNIA.NS", "CIPLA.NS",
"COALINDIA.NS", "DIVISLAB.NS", "DRREDDY.NS", "EICHERMOT.NS", "GRASIM.NS",
"HCLTECH.NS", "HDFC.NS", "HDFCBANK.NS", "HDFCLIFE.NS", "HEROMOTOCO.NS",
"HINDALCO.NS", "HINDUNILVR.NS", "ICICIBANK.NS", "INDUSINDBK.NS", "INFY.NS",
"IOC.NS", "ITC.NS", "JSWSTEEL.NS", "KOTAKBANK.NS", "LT.NS",
"M&M.NS", "MARUTI.NS", "NESTLEIND.NS", "NTPC.NS", "ONGC.NS",
"POWERGRID.NS", "RELIANCE.NS", "SBILIFE.NS", "SBIN.NS", "SHREECEM.NS",
"SUNPHARMA.NS", "TATAMOTORS.NS", "TATASTEEL.NS", "TCS.NS", "TITAN.NS",
"ULTRACEMCO.NS", "UPL.NS", "WIPRO.NS"
```

<br>

2. Basic EDA
    - obtained basic information about the dataset by computing summary statistics, such as count, mean, standard deviation, minimum, 25th percentile, median, 75th percentile, and maximum values for each numerical column.
    - generated a correlation heatmap to visualize relationships between different variables to identify any significant correlations or patterns.
    - examined the distribution of closing prices using a histogram to gain a better understanding of the distributional characteristics of the data.
    - created a line plot to visualize the temporal trends in closing prices.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; You can check the results of EDA in our Data_retrieval_and_traditional_methods in jupter folder.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; However, you should **open it in your local machine due to a big file size**

<br>

3. Traditional technical indicator
   - Three main technical indicators are used to capture the signal
        - Relative Strength Index (RSI)
        - Bollinger Bands
        - Exponential Moving Average (EMA).


<br>

4. Statistical Model (ARIMA)
    - ARIMA is used to forecast the price for strategy. To do this, ADF test is applied to check whether series are stationary.

<br>

5. DeepLearning Model (LSTM)
    - One of deep learning layer, LSTM, is used to forecast the price for strategy.
    - Data split:
        - Training dataset: 2024-02-20 to 2024-02-21
        - Validation dataset: 2024-02-22
        - Testing dataset:  2024-02-23

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; You can see the results of the ADF test and LSTM models in ARIMA_and_LSTM.

<br>

## Results
- Intraday data with smaller intervals (1m, 2m) was better for breakout strategy while larger intervals (5m, 15m, 60m)  helped smoothen the price curve, resulting in less accurate trend-following predictions.
- Traditional technical indicators such as EMA and Bollinger Band were the best for identifying reversal signals for intraday trading in 1m and 2m intervals 
- Statistical model is not appropriate for forecasting task since we cannot make series stable despite log difference.
- LSTM demonstrated good performance in predicting the stock prices of both AAPL and individual stocks of Nifty 50 with a 2-minute interval. The ability of LSTM to capture specific dynamics and trends of each stock more effectively is the reason behind its success. Intraday trading data is characterized by rapid price movements and fluctuations, which LSTM handles well.

<br>

## Acknowledge
We really appreciate the sincere support of Joe W. Byers, an instructor on our team, and Gabriella Maiello, a dean.