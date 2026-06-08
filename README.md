# Bitcoin Market Sentiment vs Hyperliquid Trader Performance Analysis

## Project Overview

This project analyzes the relationship between Bitcoin market sentiment and trader performance using two datasets:

1. Bitcoin Fear & Greed Index Dataset
2. Hyperliquid Historical Trader Dataset

The objective is to uncover hidden patterns in trader behavior, evaluate profitability under different market conditions, and generate actionable insights for sentiment-aware trading strategies.

---

## Datasets Used

### 1. Bitcoin Market Sentiment Dataset

Columns:

- date
- classification

Sentiment Categories:

- Extreme Fear
- Fear
- Neutral
- Greed
- Extreme Greed

---

### 2. Hyperliquid Historical Trader Dataset

Columns:

- Account
- Coin
- Execution Price
- Size Tokens
- Size USD
- Side
- Direction
- Timestamp IST
- Start Position
- Closed PnL
- Fee
- Trade ID
- Transaction Hash

---

## Data Preprocessing

### Sentiment Dataset

- Converted date column to datetime format.
- Normalized dates for merging.

### Trader Dataset

- Converted Timestamp IST to datetime.
- Extracted trading date.
- Merged with sentiment data using date.

```python
sentiment['date'] = pd.to_datetime(sentiment['date']).dt.normalize()

trades['Timestamp IST'] = pd.to_datetime(
    trades['Timestamp IST'],
    format='%d-%m-%Y %H:%M'
)

trades['date'] = trades['Timestamp IST'].dt.normalize()
```

---

## Analysis Performed

### 1. Trade Count by Market Sentiment

Objective:

Analyze trading activity under different market sentiments.

Key Findings:

- Fear markets generated the highest trading activity.
- Extreme Fear had the lowest participation.
- Emotional markets drive trading volume.

---

### 2. Total Profit by Market Sentiment

Objective:

Measure cumulative profits generated under each sentiment regime.

Key Findings:

- Fear and Greed periods generated most profits.
- Market sentiment significantly impacts profitability.

---

### 3. Average Profit per Trade

Objective:

Determine which sentiment produces the highest average return.

Key Findings:

- Certain sentiment regimes produce larger profits per trade.
- Market conditions influence trade quality.

---

### 4. Win Rate Analysis

Objective:

Compare percentage of profitable trades across sentiments.

Key Findings:

- Some sentiment regimes yield higher win rates.
- High win rates do not always imply maximum profits.

---

### 5. Profit Distribution and Risk Analysis

Objective:

Study risk characteristics using PnL distributions.

Key Findings:

- Fear and Extreme Fear show greater volatility.
- Outliers exist across all market conditions.
- Profitability must be analyzed alongside risk.

---

### 6. Position Size Analysis

Objective:

Analyze trader aggressiveness and capital deployment.

Key Findings:

- Larger position sizes indicate higher confidence.
- Market sentiment influences capital allocation decisions.

---

### 7. Daily Profit Trend Analysis

Objective:

Track profitability evolution over time.

Key Findings:

- Profitability varies significantly across sentiment periods.
- Certain market regimes consistently outperform others.

---

### 8. Buy vs Sell Profitability Analysis

Objective:

Compare performance of Buy and Sell trades.

Key Findings:

- Long and short strategies perform differently under varying sentiments.
- Market psychology influences directional success.

---

### 9. Top 20 Most Profitable Traders

Objective:

Identify highest-performing trader accounts.

Key Findings:

- Profits are concentrated among a small number of traders.
- Top performers significantly outperform average traders.

---

### 10. Trader Performance During Fear

Objective:

Analyze trader profitability specifically during Fear and Extreme Fear periods.

Key Findings:

- Skilled traders capitalize on panic-driven markets.
- Fear creates unique opportunities for experienced participants.

---

### 11. Correlation Analysis

Objective:

Measure relationships among sentiment, profitability, position size, and fees.

Variables Used:

- Sentiment Score
- Closed PnL
- Size USD
- Fee

Key Findings:

- Position size strongly relates to fees.
- Profitability depends on multiple interacting factors.
- Sentiment alone does not fully explain performance.

---

### 12. Hidden Pattern Discovery: Trader Segmentation

Objective:

Categorize traders based on profitability.

Method:

Quartile-based segmentation:

- Low
- Medium
- High
- Elite

Key Findings:

- Elite traders display different behavior patterns.
- Capital deployment varies significantly across trader tiers.
- Profitability is linked to trading discipline and position management.

---

## Visualizations Included

- Trade Count by Sentiment
- Total PnL by Sentiment
- Average Profit per Trade
- Win Rate by Sentiment
- PnL Distribution Boxplots
- Average Position Size by Sentiment
- Daily Profit Trends
- Buy vs Sell Profitability
- Top 20 Traders
- Top Traders During Fear
- Correlation Heatmap
- Trader Tier Analysis

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab

---

## Key Insights

1. Fear markets generated the highest trading activity.
2. Profitability varies significantly across sentiment regimes.
3. High win rates do not necessarily translate into maximum profits.
4. Fear and Extreme Fear periods exhibit greater volatility.
5. Position sizing behavior changes with market sentiment.
6. Trading success is highly concentrated among a small group of traders.
7. Elite traders demonstrate distinct capital allocation patterns.
8. Sentiment can be used as a valuable market regime indicator.
9. Market psychology plays an important role in trader decision-making.
10. Combining sentiment with trader behavior produces stronger predictive insights.

---

## Conclusion

This analysis demonstrates that market sentiment has a measurable impact on trader behavior, profitability, risk exposure, and capital allocation. Fear and Greed act as distinct market regimes, influencing how traders deploy capital and generate returns.

The findings suggest that incorporating sentiment indicators into trading strategies can improve decision-making, risk management, and overall trading performance.
