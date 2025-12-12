# Monte Carlo Portfolio Optimization

A Python implementation of Monte Carlo simulation for portfolio optimization, identifying optimal asset allocations along the efficient frontier.

## Overview

This project uses Monte Carlo simulation to generate thousands of random portfolio weight combinations and evaluate their risk-return characteristics. The analysis identifies two key portfolios: the **Maximum Sharpe Ratio** portfolio (best risk-adjusted returns) and the **Minimum Volatility** portfolio (lowest risk).

## Portfolio Universe

The analysis covers a diversified 9-stock portfolio:

| Ticker | Company | Sector |
|--------|---------|--------|
| AAPL | Apple | Technology |
| NVDA | NVIDIA | Technology |
| META | Meta Platforms | Technology |
| TSLA | Tesla | Consumer Discretionary |
| PLTR | Palantir | Technology |
| KO | Coca-Cola | Consumer Staples |
| VICI | VICI Properties | Real Estate |
| LMT | Lockheed Martin | Industrials |
| NOC | Northrop Grumman | Industrials |

## Methodology

1. **Data Collection**: Fetches 10 years of adjusted close prices from Yahoo Finance
2. **Return Calculation**: Computes daily returns and annualizes using 252 trading days
3. **Covariance Matrix**: Builds the annualized covariance matrix for portfolio variance calculation
4. **Monte Carlo Simulation**: Generates 10,000 random portfolio allocations
5. **Portfolio Metrics**: For each simulation, calculates:
   - Expected annual return
   - Portfolio volatility (standard deviation)
   - Sharpe ratio (return per unit of risk)
6. **Efficient Frontier Visualization**: Plots all portfolios with Sharpe ratio color mapping
7. **Backtesting**: Validates optimal portfolios against historical performance

## Key Outputs

- **Efficient Frontier Plot**: Scatter plot of all simulated portfolios colored by Sharpe ratio
- **Optimal Portfolio Weights**: Asset allocations for maximum Sharpe and minimum volatility portfolios
- **Performance Comparison**: Backtested returns for both optimal strategies

## Requirements

```
pandas
numpy
matplotlib
seaborn
yfinance
scikit-learn
scipy
```

## Usage

```python
# Clone the repository
git clone https://github.com/yourusername/monte-carlo-portfolio.git

# Install dependencies
pip install pandas numpy matplotlib seaborn yfinance scikit-learn scipy

# Run the notebook
jupyter notebook monte_carlo.ipynb
```

## Sample Results

The simulation identifies optimal allocations such as:

| Metric | Min Volatility | Max Sharpe |
|--------|----------------|------------|
| Expected Return | ~15.7% | ~29.1% |
| Volatility | ~15.8% | ~21.4% |
| Sharpe Ratio | ~1.00 | ~1.36 |

## Visualization

The efficient frontier plot displays:
- All 10,000 simulated portfolios as scatter points
- Color gradient indicating Sharpe ratio (yellow = higher)
- Red X marker for maximum Sharpe ratio portfolio
- Gold X marker for minimum volatility portfolio

## Limitations

- Assumes historical returns predict future performance
- Does not account for transaction costs or taxes
- Uses a simplified risk-free rate of 0%
- Past correlations may not hold in future market conditions

## License

MIT License
