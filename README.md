# Advanced Intraday Trading Models

This is a capstone project, the 10th course of the Worldquant University.  
In this module, we will try to develop our own novelty strategy for **Intraday Trading Models**.  


## Object

This project aims to contribute to the field by introducing a unique and adaptive breakout trading model specifically crafted for the Indian stock market. This involves the following:
1. Leveraging advanced algorithms
2. Real-time data integration
3. Risk management strategies
4. All validated through thorough backtesting.


## Progress

We have conducted the below for M3:
1. Data collection
    - We collected data using the yfinance library in Python, and the data selection criteria are the top 30 stocks that make up the NESI Index in India. However, one stock, MM.NS was delisted, so we collected 29 stocks' data.
2. Basic EDA
    - First of all, we try to check the listing date of the stocks, and they have various listing dates, meaning that we need to filter out the common latest date (2017-11-17) as a criterion.
    - Almost all stocks started from a similar price, but they show a very large range in price. For example, the price of Nestlé India Limited (NESTLEIND) is more than double that of others, which comes in second place.
    - We can observe that correlation is dependent on the date ranges. When we use all filtered data, it seems many stocks have high correlations, but when trying to divide data into two ranges based on COVID, there are many more stocks that don't have correlations than post-COVID in pre-COVID.
    - When we try to cluster stocks with high correlation, we can find out that clusters are larger in pre-COVID than post-COVID. It may be caused by high correlations among stocks in post-COVID.
3. Buy and Hold strategy for baseline
    - We set the baseline using the buy-and-hold strategy before we implement our own ideas. Here are two strategies: one is to just buy stocks on 2017-12-01 and sell on 2024-01-05, and the other is to do it at the start of the month and sell at the end of the month. The performance is similar until the COVID shock, but after that, the performance of the monthly buy and hold strategy is slightly better than that of the buy and hold.

You can check the above contents in the jupyter folder.


## Next Plan

We are going to design the aforementioned strategies based on the literature we have searched and papers in line with our project.
