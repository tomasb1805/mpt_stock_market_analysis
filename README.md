# Using EDA for Stock Performance Analysis

## Workflow Steps
Data Acquisition: 

The analytical pipeline begins with the retrieval of historical market data using the yfinance library.

Asset Selection:
The script targets specific banking tickers, including Banco do Brasil (BDORY), Banco Bradesco (BBD), Itaú Unibanco (ITUB), and Banco Santander (SAN).

Timeframe: 
A rolling one-year lookback period is established relative to the execution date.

Data Normalization: 
Raw multi-index data is "stacked" and reset to produce a standardized DataFrame containing timestamps, tickers, and adjusted closing prices.

## Exploratory Data Analysis (EDA)
Visual and statistical methods are employed to assess asset behavior:

Time-Series Visualization: 
Utilizing matplotlib and seaborn, the script generates line plots of Adjusted Close Prices to identify trends and volatility across the selected stocks.

Data Preparation:
Timestamps are converted to datetime objects to ensure accurate indexing for the subsequent financial calculations.

## Return and Risk Modeling
The analysis transitions from absolute prices to relative performance metrics

Daily Returns:
The script calculates the percentage change between consecutive trading days to determine asset returns.

Covariance Assessment:
A covariance matrix is computed to evaluate the co-movement of assets, a critical component for measuring systemic portfolio risk.

Mean-Variance Optimization
Applying the core tenets of Modern Portfolio Theory (MPT),
the script seeks the optimal capital distribution:

Expected Annual Metrics:
The model calculates expected annual returns and annual volatility (or Standard Deviation).

Weight Allocation:
Through mathematical optimization, the script derives the specific percentage of capital (Weights) that should be allocated to each ticker to maximize efficiency.
