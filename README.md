▶️ [Open in Google Colab](https://colab.research.google.com/drive/1CWQrnGuoCP_N5I1joNtMYMm6H9ubgtab?usp=sharing)


# 📊 Technical Report: Exploratory Data Analysis – Trading Dataset

## 📌 Assignment Introduction

As part of a data analysis assignment , this project demonstrates a complete exploratory data analysis (EDA) of a high-frequency trading dataset consisting of 104,865 execution records. The analysis combines descriptive statistics, data visualization, and interpretation of trader behavior and sentiment cycles, simulating how real-world analysts and data scientists derive actionable insights from raw financial data.

The objective was to:
- Understand distribution of trading metrics like price, token size, and profit/loss
- Analyze trader behavior during different market sentiments (fear, greed, etc.)
- Correlate trading size with PnL to check for profitability patterns
- Create visualizations to support interpretations
- Summarize everything in a structured and HR-ready format

---

## 📁 Dataset Overview

- Total Executions: 104,865
- Key Variables:
  - Execution Price
  - Token Size
  - Closed PnL (Profit/Loss)
  - Trade Size (USD)
  - Trade Side (Buy/Sell)
  - Direction (Long/Short)

---

## 🔹 1. Univariate Analysis

### 📈 Execution Price

- Mean: $29.95
- Median: $17.58 → right-skewed
- Standard Deviation: $53.83 (high volatility)
- Min: $0.000005 | Max: $463.70
- 75th Percentile: $24.26

📊 Violin Plot:

Most trades are executed at low prices, tightly clustered near the bottom, with rare outliers stretching far to the right. This pattern reflects a large number of micro-transactions and a few high-value institutional moves.

---

### 🧮 Token Size

- Mean: 4,600 tokens (inflated by outliers)
- Median: 32
- 75th Percentile: 188
- Max: 15.8 million → extreme right skew

📊 Histogram:

The majority of trades involved less than 200 tokens. The mean is not a good measure here due to extreme outliers. The token distribution supports the presence of high-frequency, small-volume strategies.

---

### 💰 Closed PnL (Profit & Loss)

- More than 50% of trades had 0 PnL
- Max Profit: +10.7 | Max Loss: -6.4
- Mean > Median → right-skewed distribution

📊 PnL Distribution Plot:

Most trades break even or yield small gains/losses. A small number of trades contribute disproportionately to total profitability, showing high volatility and possible strategy experimentation or testing.

---

## 🔄 2. Bivariate Analysis

### 💹 Trade Size (USD) vs Closed PnL

- Correlation Coefficient: 0.11 → weak positive correlation
- Most trades below $500
- Regression line is flat

📊 Regression Plot:

Trade size does not strongly correlate with profit. Some large trades even result in negative PnL, showing that capital deployment does not guarantee higher returns. Indicates non-linear or behavior-driven trading strategies.

---

## 🧠 3. Trader Behavior & Sentiment Analysis

| Sentiment     | Trader Action                            | Market Implication                   |
|---------------|-------------------------------------------|--------------------------------------|
| Fear          | Heavy selling, exits                     | Downtrend, panic                     |
| Greed         | Buying increases, long positions rise     | Uptrend, FOMO                        |
| Extreme Greed | Profit booking, spot conversions          | Market peak or possible reversal     |
| Neutral       | Balanced buy/sell                         | Range-bound market                   |

📌 Strategy Tips:

- Contrarian: During fear → Look for bounce trades
- Momentum: During greed → Follow the uptrend
- Exit/Protect: At extreme greed → Consider hedging or profit booking

---

## 📷 4. Visualizations Summary

1. 🎻 Violin Plot: Execution Price Distribution  
   - Strong right skew, majority of trades at low prices
   - Few outliers above $400

2. 📊 Histogram: Token Size (Zoomed <1000)  
   - Most trades <200 tokens
   - Heavy skew; long-tailed distribution

3. 📈 Distribution Plot: Closed PnL  
   - Over 50% of trades breakeven
   - Range: ~-6.4 to +10.7

4. 🔁 Scatter + Regression: Trade Size vs PnL  
   - Weak positive correlation
   - Flat trendline implies trade size ≠ profit

---

## ✅ Final Takeaways

- Execution prices and token sizes are highly skewed — most trades are small.
- PnL distribution shows breakeven-heavy trading with some strong outliers.
- Trade size has almost no correlation with profitability.
- Sentiment behavior aligns with classic trading psychology: fear → sell, greed → buy, extreme greed → hedge.



---

## 🙌 Thank You

This project was completed as a demonstration of data analysis capability using Python, pandas, seaborn/matplotlib, and statistical intuition. Hope it shows deep attention to technical accuracy and real-world application.

