# Monte Carlo Stock Price Simulator

A quantitative finance project that simulates future stock price movements
using Geometric Brownian Motion (GBM) and Monte Carlo methods.

Built from scratch in Python as part of a self-directed quant finance portfolio.

## The core idea

A stock price does not move in a straight line. It drifts upward on average
but is constantly pushed and pulled by random market forces. This project
models that randomness mathematically, runs 1000 simulations of one year of
trading, and produces a full risk picture of possible outcomes.

## What the simulation produces

- 1000 possible price paths for a stock over 252 trading days
- Confidence intervals showing the 5th, 25th, 50th, 75th and 95th percentiles
- A distribution of all final prices after one year
- A Value at Risk (VaR) figure: the minimum expected loss in the worst 5% of outcomes

## Key results (base parameters: $100 start, 10% drift, 20% volatility)

| Metric | Value |
|---|---|
| Median final price | ~$108 |
| 5th percentile (worst 5%) | ~$78 |
| 95th percentile (best 5%) | ~$149 |
| Value at Risk (95%) | ~$22 per $100 invested |

## The mathematics

The model uses the GBM stochastic differential equation:

Where:
- `S(0)` is the starting price
- `mu` is the expected annual return (drift)
- `sigma` is the annual volatility
- `Z` is a standard normal random variable
- The `0.5 * sigma^2` term corrects for volatility drag

## Tools used

- Python 3
- Jupyter Notebook
- numpy (simulation and vectorised computation)
- matplotlib (visualisation)

## How to run this project

```bash
git clone https://github.com/faith-dev122/monte-carlo-stock-simulator.git
cd monte-carlo-stock-simulator
pip install numpy matplotlib scipy jupyter
jupyter notebook
```

Open `monte_carlo_simulator.ipynb` and run all cells in order.