# Project Background
This analysis serves as a quantitative evaluation of the risk-adjusted performance of four major banking equities: **Banco do Brasil (BDORY)**, **Banco Bradesco (BBD)**, **Itaú Unibanco (ITUB)**, and **Banco Santander (SAN)**. Operating within the Brazilian and global financial sectors, these institutions' market behaviors were scrutinized from the perspective of a data analyst to optimize a representative portfolio. 

Insights and recommendations are provided on the following key areas:

- **Momentum and Divergence**: Comparative analysis of price trajectories and sector decoupling.
- **Volatility Catalysts**: Identification of macroeconomic and regulatory events affecting asset stability.
- **Risk Modeling**: Implementation of Modern Portfolio Theory (MPT) to evaluate efficiency.
- **Capital Allocation**: Mathematical derivation of optimal weights via Sharpe Ratio maximization.

The Python implementation utilizing `yfinance`, `pandas`, and `numpy` for this analysis is available in the repository.

# Data Structure & Initial Checks
The primary dataset consists of historical adjusted closing prices and trading volumes retrieved via the `yfinance` library. The data was processed into a multi-index DataFrame, subsequently "stacked" and reset to produce a standardized format for time-series analysis.

- **Temporal Coverage**: A rolling one-year lookback period through late 2025.
- **Attributes**: Timestamps, Tickers, and Adjusted Closing Prices.
- **Integrity**: Data was normalized to ensure accurate indexing for financial calculations.



# Executive Summary
### Overview of Findings
The analysis indicates that a portfolio optimized for risk-adjusted returns heavily favors **Santander (SAN)** and **Banco do Brasil (BDORY)**. The optimization process identified that SAN significantly outperformed the cohort, despite a temporary volatility event in April 2025 linked to UK regulatory shifts. The resulting optimized portfolio yields an **Expected Annual Return of 28.5%** with an **Annualized Volatility of 24.3%**.


# Insights Deep Dive
### Insight 1: Price Momentum & Cohort Divergence
<img width="784" height="384" alt="adj-close" src="https://github.com/user-attachments/assets/176ef2a5-3449-44dd-966f-28b29d31bed2" />
<img width="784" height="384" alt="volume-san" src="https://github.com/user-attachments/assets/74a88482-ab7f-4433-a274-40e8bad23589" />

* **Santander Dominance**: SAN demonstrated consistent outperformance relative to the other three tickers throughout the observed timeframe.
* **April Divergence**: ITUB and BDORY initially shared similar performance characteristics before diverging significantly in April 2025.
* **Lagging Recovery**: BBD functioned as the least performing stock for the majority of the period but showed convergence with BDORY by the end of 2025.
  


### Insight 2: Volatility and Technical Indicators
<img width="784" height="384" alt="macd-san" src="https://github.com/user-attachments/assets/9fb0ec2a-c4a5-4bef-b582-b944791849ee" />

* **Moving Average Support**: MACD analysis (50 and 200-day rolling averages) identified a localized period of weakness for SAN in late April 2025.
* **External Catalysts**: The April volatility coincided with ex-dividend dates and market concerns regarding changes in UK Ring Fencing policies.
* **Liquidity Validation**: Trading volumes confirmed institutional resilience, as the stock maintained its positive trajectory following the Q1 performance assessment.


### Insight 3: Covariance and Sectoral Correlation
<img width="684" height="584" alt="corr-matrix" src="https://github.com/user-attachments/assets/b9e7d0d9-df92-400d-973d-3695ed9c59e3" />

* Systemic Correlation Density. A robust positive correlation of 0.73 exists between Banco Bradesco (BBD) and Itaú Unibanco (ITUB), indicating high * susceptibility to identical systemic shocks within the Brazilian retail banking sector.
* Diversification Potential of SAN. Banco Santander (SAN) exhibits the lowest correlation coefficients across the cohort, particularly with BDORY
* (0.35), suggesting its inclusion reduces aggregate portfolio variance.
* Inter-Asset Neutrality. The correlation between SAN and BBD (0.40) remains moderate, facilitating a more efficient risk-frontier compared to a portfolio concentrated solely in BBD and ITUB.
* BDORY Independence. Banco do Brasil (BDORY) maintains relatively low co-movement with both SAN (0.35) and BBD (0.44), functioning as a secondary diversifier for the optimized portfolio.

### Insight 4: Statistical Distribution of Daily Returns
<img width="784" height="384" alt="d-returns-kde" src="https://github.com/user-attachments/assets/7b7187d8-ed1d-4929-8733-a2837e746713" />

* Leptokurtic Tendencies in BBD. The daily return distribution for BBD (green) demonstrates high kurtosis with a sharp central peak near 0.00, indicating a high frequency of small price movements punctuated by extreme outliers.

* Return Dispersion in ITUB and BDORY. ITUB and BDORY exhibit broader Kernel Density Estimation (KDE) curves, signifying higher variance and a wider range of daily performance outcomes compared to BBD.

* Outlier Analysis and Fat Tails. Both BBD and BDORY display significant "fat tails," with BBD recording positive extreme returns exceeding 0.15 and BDORY recording negative outliers below -0.10.

* Volatility Clustering. The overlapping distributions of SAN and ITUB suggest similar volatility regimes, though SAN’s distribution is slightly more centered, aligning with its role as a primary stabilizer in the optimized weights.

### Insight 5: Mean-Variance Optimization
The portfolio optimization utilized the **Sharpe Ratio** to identify the tangency portfolio on the Efficient Frontier.

<img width="627" height="433" alt="efficient-frontier-mpt" src="https://github.com/user-attachments/assets/69bd3929-2550-4d02-9aed-d9aee17e0a02" />


# Recommendations:
Based on the derived optimal weights and performance metrics, the following allocations are recommended:

* Allocate **80.3%** of capital to **SAN** and **19.7%** to **BDORY**. **This configuration maximizes the expected return per unit of risk based on historical variance.**
* Maintain a **0%** allocation for **BBD** and **ITUB**. **These assets currently contribute insufficient marginal returns relative to their volatility within the cohort.**
* Monitor UK and Brazilian regulatory updates closely. **The sensitivity of SAN to Ring Fencing policies suggests that macroeconomic shifts are primary drivers of idiosyncratic risk.**

# Assumptions and Caveats:
* **Stationarity**: The model assumes that historical returns and covariance structures will persist in the future.
* **Normality**: The use of standard deviation as a risk proxy assumes that asset returns follow a normal distribution, ignoring potential "black swan" events.
* **Lookback Period**: The optimization is strictly based on a one-year rolling window; varying the timeframe may yield different optimal weights.
