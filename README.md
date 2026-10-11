# portfolio-optimization-macedonian-stocks-SLSQP-2026
The following project served mainly as an academic exercise with the usage of Python to explore non-linear optimization methods such as SLSQP in the area of Finance and Portfolio Modelling.
Due to the project rules mandated by the professor as well as data availability, there are significant limitations, as noted under ## Limitations.

5 Macedonian stocks were analysed using Markowitz optimisation framework with individual securities' weights derived using constrained SLSQP iterations.
The analysis was made using 36 individual stock-price observations resulting in 35 observations after calculating log returns, covering the period 2023-2025. 

The SLSQP derived portfolio weights portfolio performance was compared to a "Naive Portfolio"(equally weighted portfolio) as well as the MBI-10 benchmark index. 

Another aspect was also taken into consideration regarding the treatment of the extreme outliers during the calculation of the stock beta coefficients. A hypothesis was made that the usage of a 
Huber M-Estimator would yield more accurate and statistically significant beta-coefficients, which was later determined to yield no different results than the regular OLS regression. 

An out of sample test wasn't made due to very limited stock activity in the following months after the optimization was done, therefore leaving historical data as the only benchmark for hypothetical 
performance tracking. **The project will be updated in the future for an adequate out of sample test!**

## Methodology

- Log returns
- Correlation analysis
- Value at Risk (VaR)
- Return/Risk Metric as objective
- Constrained SLSQP optimization
- MBI10 benchmark comparison
- Drawdown graph
- Cumulative performances graph
- Theoretical dollar measured profit graph

## Technologies

- Python
- pandas
- NumPy
- statsmodels
- SciPy
- matplotlib
- seaborn

## SLSQP Optimization results

The SLSQP optimization produced the following portfolio weights:

| Stock   | Weight |
|---------|--------|
| Replek  | 43.62%   |
| TTK     | 0%     |
| Makstil | 20.83%  |
| Tikves  | 35.55%   |
| Okta    | 0%     |

An equally weighted portfolio was also constructed to provide a benchmark for evaluating the optimized portfolio.

| Stock   | SLSQP Weights| Equal weights| 
|---------|--------|--------|
| Replek  | 43.62%    | 20%    |
| TTK     | 0%     | 20%    |
| Makstil | 20.83%    | 20%    |
| Tikves  | 35.55%    | 20%    |
| Okta    | 3%     | 20%    |

| Portfolio | Returns(Annualized) | Return/Risk(Annualized) |
|-----------|---------|-------------|
| SLSQP     | 14,9%  | 1,25         |
| Equal     | 11%     | 0,85        |
| Stock Index| 18,6%  | 1,64        |

| Portfolio           | Q1     | Q3    | VaR    |
|---------------------|--------|-------|--------|
| MBI-10              | -0.99% | 2.95% | -1.93% |
| Equal Weights       | -1.02% | 1.99% | -2.82% |
| SLSQP               | -0.53% | 2.42% | -2.94% |

The hypothetical returns of the portfolios are calculated using the already available historical data. 


| Portfolio      | USD Profit (Cumulative) | Drawdown | Cumulative Performance | 
|----------------|------------------------:|---------:|-----------------------:|
| MBI-10         | ~$723                   | -7.23%    | 72.32%                  |
| Equal Weights  | ~$380                   | -10.9%    | 38%                 |
| SLSQP          | ~$544                   | -8.37%    | 54.45%                 |


## Conclusion

Under the assumptions from the model, the SLSQP portfolio did not outperform the market index MBI-10, nor the equally weighted portfolio. 
The risk-adjusted return for the SLSQP portfolio is slightly higher than the equally weighted portfolio and noticeably lower than the MBI-10 Index risk-return.

These results illustrate the limitations of relying on a simple model and are broadly consistent with the idea that
simple historical optimization may not generate excess returns relative to the market benchmark.


## Limitations
The analysis is based on a limited sample of 35 monthly observations due to course requirements. It does not account for:

-  Transaction costs
-  Liquidity constraints beyond the imposed portfolio bounds
-  The risk-free rate
-  Out-of-sample performance
-  Changes in market conditions
-  Portfolio rebalancing costs
-  Estimation uncertainty in expected returns and covariance

Consequently, the results should be interpreted as an academic, in-sample analysis rather than evidence of the future performance of the optimized portfolio.
