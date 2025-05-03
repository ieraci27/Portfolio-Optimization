# Momentum-Based Portfolio Optimization

This repository contains a Python implementation of a momentum-based stock portfolio strategy, optimized using the Markowitz mean-variance framework.  
The strategy compares:

✅ A **12-month momentum portfolio**  
✅ A **combined 12-month and 1-month momentum portfolio**  
✅ The **S&P 500 benchmark**

The goal is to analyze and compare portfolio performance and risk metrics over time.

---

## 📈 Strategy Overview

### 🟢 1. 12-Month Momentum Strategy

- **Idea:** Select stocks that have performed best over the past year, following the momentum principle that "winners keep winning."
- **Signal:** 12-month historical return, computed at a monthly frequency.
- **Selection:** Top 15% of stocks ranked by their past 12-month return.
- **Rebalancing:** Monthly — every month, the top 15% stocks are reselected.
- **Weighting:** Markowitz mean-variance optimization to maximize the portfolio’s Sharpe ratio, subject to long-only weights that sum to 1.

---

### 🟣 2. Combined 12-Month + 1-Month Momentum Strategy

- **Idea:** Combine both medium-term (12 months) and short-term (1 month) momentum to capture persistent trends and recent accelerations.
- **Signal:**
    - 12-month historical return (medium-term momentum)
    - 1-month historical return (short-term momentum)
- **Selection:** 
    - Top 15% of stocks by 12-month return.
    - Top 15% of stocks by 1-month return.
- **Allocation:** 
    - 50% of portfolio capital to the 12-month top momentum stocks.
    - 50% of portfolio capital to the 1-month top momentum stocks.
- **Weighting:**  
    - Each half optimized separately using Markowitz optimization.
    - Final combined portfolio: average of the two optimized weight vectors.

---

## 💥 Features

- Historical price data loading and cleaning  
- Momentum signal computation  
- Stock selection by momentum percentile  
- Markowitz optimization with Sharpe maximization  
- Daily portfolio simulation with monthly rebalancing  
- Performance comparison against the S&P 500  
- Calculation of key metrics:
    - Total Return
    - Annualized Volatility
    - Sharpe Ratio
    - Sortino Ratio
    - Max Drawdown
    - Value at Risk (VaR 95%)

- Visualization:
    - Cumulative returns chart
    - Drawdown chart
    - Performance metrics summary table

---

## 🔧 Requirements

- Python ≥ 3.7  
- pandas  
- numpy  
- scipy  
- matplotlib  
- pandas_datareader

Install dependencies:
```bash
pip install pandas numpy scipy matplotlib pandas_datareader
