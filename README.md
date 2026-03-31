# Portfolio-Optimization-and-Risk-Tool

Analyzes user-defined portfolios of stocks, ETFs, and bond funds using key risk metrics and applies Modern Portfolio Theory (MPT) to identify optimal portfolio allocations via the Efficient Frontier and Capital Market Line.

Built in Python and designed to run fully in Google Colab — no setup required.

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
*Add screenshot here*

### Correlation Matrix
*<img width="610" height="508" alt="Screenshot 2026-03-30 at 10 47 51 PM" src="https://github.com/user-attachments/assets/db81e36e-60e7-4472-bdc4-7a30e589e43e" />*


### Optimal Portfolio Allocations
*Add screenshot here*

### Cumulative Returns
*Add screenshot here*

---

## 🚀 How to Run

1. Open the notebook in Google Colab: [Open in Colab](https://colab.research.google.com/)
2. Upload the `.ipynb` file or open directly from GitHub
3. Edit the `TICKERS` list in **Section 2** with your desired stocks/ETFs
4. Run all cells from top to bottom

No API keys required. All data is fetched free from Yahoo Finance.

---

## ⚙️ Configuration

All user settings are in **Section 2** of the notebook:

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

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| Python | Core language |
| yfinance | Live market data from Yahoo Finance |
| NumPy / Pandas | Data processing and risk calculations |
| Plotly | Interactive charts and visualizations |
| Google Colab | Cloud-based notebook environment |

---

## 📐 Finance Concepts Demonstrated

- **Modern Portfolio Theory (MPT)** — Harry Markowitz (1952) framework for portfolio optimization
- **Efficient Frontier** — curve of portfolios maximizing return for a given level of risk
- **Capital Market Line (CML)** — optimal risk/return line from the risk-free rate through the Max Sharpe portfolio
- **Sharpe Ratio** — excess return per unit of risk
- **Historical VaR** — percentile-based loss estimation from actual return distribution
- **Beta** — systematic market risk relative to S&P 500
- **Log Returns** — continuously compounded returns used for statistical accuracy

---

## 🔮 Future Improvements

- Replace Monte Carlo simulation with SciPy quadratic optimization for mathematically exact efficient frontier
- Add CVaR (Conditional Value at Risk / Expected Shortfall) alongside VaR
- Add portfolio rebalancing simulation over time
- Support for commodity futures and crypto with data cleaning pipeline

---

## 👤 Author

**Ivry Sasson**  
Finance & Economics | University of Pittsburgh  
[LinkedIn](https://linkedin.com/in/ivry-sasson) | ivrysasson@gmail.com
