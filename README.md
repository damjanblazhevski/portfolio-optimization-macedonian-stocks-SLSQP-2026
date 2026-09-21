# portfolio-optimization-macedonian-stocks-SLSQP-2026
5 Macedonian stocks were analysed using Markowitz optimisation framework with individual securities' weights derived using constrained SLSQP iterations.
The analysis was made using 36 individual stock-price observations resulting in 35 observations after calculating log returns, covering the period 2023-2025. 

## Methodology

- Log returns
- Correlation analysis
- Value at Risk (VaR)
- Markowitz portfolio optimization
- Constrained SLSQP optimization
- MBI10 benchmark comparison

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
| Replek  | 28%    |
| TTK     | 0%     |
| Makstil | 45%    |
| Tikves  | 24%    |
| Okta    | 3%     |

An equally weighted portfolio was also constructed to provide a benchmark for evaluating the optimized portfolio.

| Stock   | SLSQP Weights| Equal weights| 
|---------|--------|--------|
| Replek  | 28%    | 20%    |
| TTK     | 0%     | 20%    |
| Makstil | 45%    | 20%    |
| Tikves  | 24%    | 20%    |
| Okta    | 3%     | 20%    |

| Portfolio | Returns | Return/Risk |
|-----------|---------|-------------|
| SLSQP     | 10,53%  | 1,1         |
| Equal     | 11%     | 0,85        |
| Stock Index| 18,6%  | 1,64        |

| Portfolio           | Q1     | Q3    | VaR    |
|---------------------|--------|-------|--------|
| MBI-10              | -0.99% | 7.22% | -1.93% |
| Equal Weights       | -1.02% | 2.00% | -2.80% |
| SLSQP               | -0.17% | 5.71% | -2.83% |

The hypothetical returns of the portfolios are calculated using the already available historical data. 

## Conclusion

Under the assumptions from the model, the SLSQP portfolio did not outperform the market index MBI-10. 
The risk-adjusted return for the SLSQP portfolio is slightly higher than the equally weighted portfolio, 
although yielding slightly lower returns. 

These results illustrate the limitations of relying on a simple model and are broadly consistent with the idea that
simple historical optimization may not generate excess returns relative to the market benchmark.


## Limitations
The analysis is based on a limited sample of 35 monthly observations due to course requirements. It does not account for:

Transaction costs
Liquidity constraints beyond the imposed portfolio bounds
The risk-free rate
Out-of-sample performance
Changes in market conditions
Portfolio rebalancing costs
Estimation uncertainty in expected returns and covariance

Consequently, the results should be interpreted as an academic, in-sample analysis rather than evidence of the future performance of the optimized portfolio.
