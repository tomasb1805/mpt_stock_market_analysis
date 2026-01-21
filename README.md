# Using EDA for Stock Performance Analysis

A year ago I became increasingly interested in how the stock market worked, but I was still unsufficently skilled with Data Analysis tools to achieve a satisfactory results for a topic this complex.
Today, I want to deepen my understanding of 4 stocks I have been observing for a while, using an exploratory approach also known as Exploratory Data Analysis, or EDA for short. 

Before the

Beneath you can find the project structure and setup, that are not to be considered financial advice in any form or way, and to be understood only as demonstrative and/or illustrative endeavours.

## The Setup:
#### Data Acquisition: 

The analytical pipeline begins with the retrieval of historical market data using the yfinance library. The asset selection consist in 4 banking tickers:  Banco do Brasil (BDORY), Banco Bradesco (BBD), Itaú Unibanco (ITUB), and Banco Santander (SAN).

#### Establishing a Timeframe: 

A rolling one-year lookback period is established from the date the audience will interact with the script and the data then normalized into a raw multi-index data that is "stacked", then the index gets reset to produce a standardized DataFrame containing timestamps, tickers, and adjusted closing prices.

#### Data Preparation and Time-Series visualization: 
Since this is a time-series, to visualize the data utilizing Matplotlib and Seaborn we need to convert the Timestamps to a datetime object to ensure accurate indexing for the subsequent financial calculations, and then generate the line plots of Adjusted Close Prices with a script that makes identifing trends and the volatility across the selected securities easier to achieve.

## The Analysis 
Now for the actual exploration phase:
More often than not, plotting the data will generate more insights thanks to the ability of the human brain to better percieve changes visually.

#### Plotting the Adjusted Close prices over time

The first step is to understand the performance of the stocks for the year taken into consideration, by plotting the adjusted close price for each security as time passes, this will get us familiar with the raw output of each:

<img width="608" height="570" alt="Adjusted Close Price for each Security" src="https://github.com/user-attachments/assets/a3df2989-8789-43fd-b64f-7056c1c56d46" />

Some first conclusion can be extracted from this basic line chart. As a overall trend, Santander tends to massively outperform all the other tickers,
Itaú and Banco Central do Brasil initially had similiar performance before starting to diverge in April 2025, and finally Banco Bradesco closes the cohort as the least performing stock, but gradually gaining track over time and achieving a similar performance to BDORY by the end of 2025.

This can be a first step to dive deeper into the exploration: Why the two similar stocks diverged? It was an external event or the two companies perfomances caused this change? Why Banco Bradesco is struggling when compared to the others?

Since this is a portofolio project to showcase my skills in Data Analysis, such as implementing Python code and using other tools of the trade, I will bring the investigation to a different direction but it's easy to understand how a simple but trusted tool like a Line chart can  generate many insights and lead to very different paths depending on the goal of the analysist.

#### Plotting Rolling Averages


For the next steps we will assess the asset behavior considering the moving averages in a 50 and 200 days period, which in finance i also known with the name "MACD" or "Moving Average Convergence/Divergence" and is used to understand the performance of a stock on a wider timescale. For demostration purposes only the Santander MACD and Trading Volumes will be shown, but in the code the output produces averages and volumes for all four stocks 

<img width="608" height="570" alt="Santander MACD" src="https://github.com/user-attachments/assets/293a82cb-41c9-4b88-bddd-ed3ebdfce536" />

<img width="608" height="570" alt="Santander Trading Volumes" src="https://github.com/user-attachments/assets/bc6ebeaa-3435-460e-ab8a-d61183816480" />

It's easy to notice that this stock had a moment of weakness at the end of April 2025, this can be established due to several factors including an ex-dividend date, unsatisfactory Q1 performance according to some analysts and investors and on a macro scale consideration some concerns around changes in the UK Ring Fencing policies (regulatory laws on the separation of capital for retail and investing purposes established after the 2008 crisis aftermath). These changes could have severly impacted the performance of non-UK banks operating on British soil.

Despite these issues, the company continued to delivere and was consistent in its business strategy and goals, which earned back the trust of investor and maintained the overall very positive performance until the end of 2025.

## Return and Risk Modeling
This analysis transitions from absolute pricing to relative performance metrics, utilizing Modern Portfolio Theory (MPT) framework to evaluate risk-adjusted returns via the Sharpe Ratio.

- Daily Returns:
Calculation of percentage variance between consecutive trading sessions to establish periodic asset performance.

- Covariance Assessment:
Computation of a covariance matrix to quantify asset co-movement and aggregate systemic risk.

- Mean-Variance Optimization: 
Algorithmic determination of optimal fund allocation to maximize efficiency per unit of risk.

- Annualized Metrics:
Projection of expected annual returns and volatility (standard deviation).

- Weight Allocation:
Mathematical derivation of capital distribution across tickers to achieve an optimized portfolio structure.

## Conclusions:
