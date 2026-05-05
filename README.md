# Portfolio-Optimization-and-Risk-Tool

Analyzes user-defined portfolios of stocks, ETFs, bond funds, and REITs  using key risk metrics and applies Modern Portfolio Theory (MPT) to identify optimal portfolio allocations via the Efficient Frontier and Capital Market Line.

Built in Python and designed to run fully in Google Colab, no setup required.


## Acknowledgments
Built with assistance from Claude

---

## Features

- **Sharpe Ratio** — measures risk-adjusted return relative to the current 3-month T-bill rate (fetched live)
- **Value at Risk (VaR)** — estimates worst expected daily loss at 95% confidence
- **CVaR (Conditional Value at Risk)** — average loss on the worst 5% of days, 
  a more accurate tail risk measure than VaR
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
<img width="855" height="602" alt="Screenshot 2026-03-30 at 11 07 28 PM" src="https://github.com/user-attachments/assets/4450a654-e2ad-4bb3-9dd3-b09936b8b6fe" />



### Correlation Matrix
<img width="605" height="503" alt="Screenshot 2026-03-30 at 11 06 46 PM" src="https://github.com/user-attachments/assets/4caf395b-38b9-42ac-8797-a37deb162d33" />



### Optimal Portfolio Allocations
<img width="856" height="454" alt="Screenshot 2026-03-30 at 11 08 00 PM" src="https://github.com/user-attachments/assets/a67f3ece-803e-4f72-ae60-785398e939dc" />



### Cumulative Returns
<img width="854" height="502" alt="Screenshot 2026-03-30 at 11 09 45 PM" src="https://github.com/user-attachments/assets/b1821707-80d3-45c7-9744-730c30fe6654" />




---

## How to Run

1. Open the notebook in Google Colab: [Open in Colab](https://colab.research.google.com/)
2. Upload the `.ipynb` file or open directly from GitHub
3. Edit the `TICKERS` list in **Section 2** with your desired stocks/ETFs
4. Run all cells from top to bottom

No API keys required. All data is fetched free from Yahoo Finance.

---

## Configuration

All parameters are in **Section 2** of the notebook:
Tickers, time frame, VaR confidence level, and number of simulation portfolios are all customizable.

```python
# Supported: Individual stocks (AAPL), ETFs (SPY, VOO), Bond funds (TLT, AGG), REITs (VNQ)
TICKERS = ['SPY', 'TLT', 'GOOGL', 'JPM', 'VNQ']

# Automatically set to today's date, rolling 7-year window
END_DATE   = date.today().strftime('%Y-%m-%d')
START_DATE = (date.today() - relativedelta(years=7)).strftime('%Y-%m-%d')

# Risk-free rate — fetched dynamically in Section 1 from Yahoo Finance (^IRX, 3-month T-bill)

# 95% confidence — industry standard
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
- Add portfolio rebalancing simulation over time
- Support for commodity futures and crypto with data cleaning pipeline

---

