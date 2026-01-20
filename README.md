# Using EDA for Stock Performance Analysis

A year ago I became increasingly interested in how the stock market worked, but I was still unsufficently skilled with Data Analysis to translate my analytical knowledge into this complex topic.
Today, I want to deepen my understanding of 4 stocks I have been watching for a while using an exploratory approach, also known as Exploratory Data Analysis, or EDA. 
Beneath the project structure, setup and steps are described. 

## Workflow Steps
Data Acquisition: 

The analytical pipeline begins with the retrieval of historical market data using the yfinance library. The asset selection consist in 4 banking tickers:  Banco do Brasil (BDORY), Banco Bradesco (BBD), Itaú Unibanco (ITUB), and Banco Santander (SAN).

Timeframe: 
A rolling one-year lookback period is established from the date the audience will interact with the script and the data then normalized into a raw multi-index data that is "stacked", then the index gets reset to produce a standardized DataFrame containing timestamps, tickers, and adjusted closing prices.

## Exploratory Data Analysis (EDA)
Now for the actual exploration phase:
More often than not, plotting the data will generate more insights thanks to the ability of the human brain to better percieve changes visually.
This part will assess the asset behavior considering moving averages in 50 and 200 days period, which in finance is known with the name MACD or Moving Average Convergence/Divergence and is used to understand the performance of a stock on a wider timescale

Data Preparation and Time-Series visualization: 
Since this is a time-series, to visualize the data utilizing Matplotlib and Seaborn we need to convert the Timestamps to a datetime object to ensure accurate indexing for the subsequent financial calculations, and then  generates the line plots of Adjusted Close Prices with a script  that makes identifing trends and the volatility across the selected securities.


## Return and Risk Modeling
The following analysis transitions from absolute prices to relative performance metrics, including Daily Returns, Covariance, Mean-Covariance, and then proceeds to calculate the Sharpe Ratio (also know as Risk-Adjusted Return) to model the return when taking into consideration risk exposure.

Daily Returns:
The analysis here calculates the percentage change between consecutive trading days, and therefore determines the asset returns over the established period of time.

Covariance Assessment:
A covariance matrix is computed to evaluate the co-movement of assets, and therefore is a critical component for measuring the systemic risk linked to the portfolio.

Mean-Variance Optimization
This is a standard application of Modern Portfolio Theory (MPT),
to optimize the fund allocation for each stock.

Expected Annual Metrics:
Here the modeling projects the expected annual returns and annual volatility figures (or Standard Deviation).

Weight Allocation:
Through mathematical optimization, the script derives the specific percentage of capital (Weights) that should be allocated to each ticker to maximize efficiency.
