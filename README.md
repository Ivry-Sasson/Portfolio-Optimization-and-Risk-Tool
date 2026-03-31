# Portfolio-Optimization-and-Risk-Tool

Analyzes user-defined portfolios of stocks, ETFs, and bond funds using key risk metrics and applies Modern Portfolio Theory (MPT) to identify optimal portfolio allocations via the Efficient Frontier and Capital Market Line.

Built in Python and designed to run fully in Google Colab, no setup required.

---

## Features

- **Sharpe Ratio** — measures risk-adjusted return relative to the current 3-month T-bill rate (fetched live)
- **Value at Risk (VaR)** — estimates worst expected daily loss at 95% confidence using historical simulation
- **Maximum Drawdown** — measures largest peak-to-trough decline over the analysis period
- **Beta** — measures sensitivity to S&P 500 market movements
- **Correlation Matrix** — heatmap showing how assets move relative to each other
- **Efficient Frontier** — Monte Carlo simulation of 10,000 random portfolios plotted by risk vs return
- **Capital Market Line** — identifies the optimal risk/return tradeoff anchored at the risk-free rate
- **Optimal Portfolio Allocations** — Max Sharpe and Minimum Variance portfolios with weight breakdowns
- **Cumulative Returns Chart** — growth of $1 invested with key market event shading (COVID, 2022 Bear Market, 2025 Tariff Selloff)

---

## Screenshots

### Efficient Frontier & Capital Market Line
*<img width="855" height="606" alt="Screenshot 2026-03-30 at 10 49 07 PM" src="https://github.com/user-attachments/assets/384af53d-45ea-48e9-aa2d-089ac5fef32d" />*


### Correlation Matrix
*<img width="610" height="508" alt="Screenshot 2026-03-30 at 10 47 51 PM" src="https://github.com/user-attachments/assets/db81e36e-60e7-4472-bdc4-7a30e589e43e" />*


### Optimal Portfolio Allocations
*<img width="857" height="454" alt="Screenshot 2026-03-30 at 10 49 46 PM" src="https://github.com/user-attachments/assets/27916b7a-785b-41f0-80cb-77e825100b80" />*


### Cumulative Returns
*<img width="856" height="503" alt="Screenshot 2026-03-30 at 10 50 28 PM" src="https://github.com/user-attachments/assets/5c8c552c-9987-4999-8358-01a52f6901a9" />*


---

## How to Run

1. Open the notebook in Google Colab: [Open in Colab](https://colab.research.google.com/)
2. Upload the `.ipynb` file or open directly from GitHub
3. Edit the `TICKERS` list in **Section 2** with your desired stocks/ETFs
4. Run all cells from top to bottom

No API keys required. All data is fetched free from Yahoo Finance.

---

## Configuration

All user inputs are in **Section 2** of the notebook:

```python
# Supported: Individual stocks (AAPL), ETFs (SPY, VOO), Bond funds (TLT, AGG), REITs (VNQ)
TICKERS = ['SPY', 'TLT', 'GOOGL', 'JPM', 'VNQ']

# Automatically set to today's date, rolling 7-year window
END_DATE   = date.today().strftime('%Y-%m-%d')
START_DATE = (date.today() - relativedelta(years=7)).strftime('%Y-%m-%d')

# Fetched live from Yahoo Finance (^IRX)
RISK_FREE_RATE = ...

# 95% confidence — industry standard (banks use 0.99 under Basel regulations)
VAR_CONFIDENCE = 0.95

# Increase for a smoother efficient frontier
NUM_PORTFOLIOS = 10000
```

---

## Technologies Used

| Tool | Purpose |
|---|---|
| Python | Core language |
| yfinance | Live market data from Yahoo Finance |
| NumPy / Pandas | Data processing and risk calculations |
| Plotly | Interactive charts and visualizations |
| Google Colab | Cloud-based notebook environment |

---

## Future Improvements

- Replace Monte Carlo simulation with SciPy quadratic optimization for mathematically exact efficient frontier
- Add CVaR (Conditional Value at Risk / Expected Shortfall) alongside VaR
- Add portfolio rebalancing simulation over time
- Support for commodity futures and crypto with data cleaning pipeline

---

## Author

**Ivry Sasson**  
Finance & Economics | University of Pittsburgh  
[LinkedIn](https://linkedin.com/in/ivry-sasson) | ivrysasson@gmail.com
