
# 📊 Tesla Stock Analysis – Capstone Project

This project presents a comprehensive, end-to-end analysis of Tesla's stock using historical price data, revenue data, technical indicators, and machine learning models. The goal is to model Tesla's future price movement, simulate basic trading strategies, and evaluate predictive performance using a wide range of financial metrics and visualizations.

---

## 📁 Contents

- `Stock_analysis.ipynb` — Core notebook containing all analysis
- `README.md` — This document
- 📊 Visuals — Model outputs and evaluation charts (confusion matrix, ROC curves, strategy simulations)

---

## 📥 Data Sources

- **Stock Prices**: Pulled using [yfinance](https://pypi.org/project/yfinance/)
- **Revenue Data**: Web-scraped from [IBM's sample project page](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)

---

## 🧭 Project Workflow

### 1. Data Loading
- Tesla daily stock prices via `yfinance`
- Quarterly revenue scraped via `requests` and `BeautifulSoup`

### 2. KPI Dashboard
Key performance indicators calculated:
- 📈 1-Year price return
- 📉 30-day average volume
- 💹 Annualized volatility
- 💰 Revenue growth (past 5 quarters)

### 3. Feature Engineering
All technical indicators and predictive features were calculated in a single section:
- `SMA_5`, `SMA_20` — Moving Averages
- `RSI` — Relative Strength Index
- `MACD` — Moving Average Convergence Divergence
- `Momentum` — via stochastic oscillator
- `Lag1`, `Lag2`, `Lag3` — Prior return values
- `Target_Return` — Next-day percentage return
- `Target_Class` — Binary label for return direction

Cleaned and merged into `model_df`.

### 4. Machine Learning Modeling

#### 🔢 Regression (Gradient Boosting Regressor)
- Goal: Predict **next-day % return**
- Evaluation: RMSE

#### ✅ Classification (Gradient Boosting Classifier)
- Goal: Predict **direction of return (up/down)**
- Evaluation:
  - Accuracy, F1 Score
  - ROC-AUC
  - Confusion Matrix

#### 🧠 Additional Models
- `RandomForestClassifier`
- `LogisticRegression`
- ROC Curves used to compare models

### 5. Trading Strategy Simulation
- Used model predictions to simulate:
  - 🚀 Buy if predicted return > 0
  - 💰 Hold cash otherwise
- Portfolio value vs Tesla stock plotted
- Risk-adjusted metrics:
  - CAGR
  - Sharpe Ratio
  - Max Drawdown

---

## 📊 Example Outputs

- Confusion Matrix Heatmaps
- Actual vs Predicted Return Plots
- Portfolio vs Market Comparison Charts
- Feature Importance Graphs

---

## 📦 Libraries Used
- yfinance
- pandas,numpy
- ta
- scikit-learn
- plotly,seaborn,matplotlib
- beatifulsoup4,requests


---

## 🧠 Key Takeaways

- Technical indicators can help forecast return direction
- Gradient Boosting models performed better than baseline
- Predictive power was limited — good starting point, but room for multi-feature and macroeconomic improvements
- Strategy backtest allowed real-world portfolio simulation
- Project showcases a full data-to-decision analytics pipeline

---

## 🚀 Future Improvements

- Hyperparameter tuning
- Include macroeconomic indicators (e.g., inflation, Fed rates)
- Use multi-day return horizons (not just next day)
- Deploy as a Streamlit dashboard (for interactivity)
- Expand to sector comparison (Tesla vs EV market)



