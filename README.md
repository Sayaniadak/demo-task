# Trader Performance vs Bitcoin Market Sentiment Analysis

Exploring the relationship between Hyperliquid trader performance and Bitcoin Fear/Greed market sentiment, to uncover patterns that can inform smarter trading strategies.

## Overview

This project analyzes two datasets:

1. **Bitcoin Market Sentiment Dataset** — daily Fear/Greed Index classification
   - Columns: `Date`, `Classification` (Extreme Fear / Fear / Neutral / Greed / Extreme Greed)

2. **Historical Trader Data (Hyperliquid)** — ~3.4M individual trade records
   - Columns: `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, `Timestamp IST`, `Start Position`, `Direction`, `Closed PnL`, `Transaction Hash`, `Order ID`, `Crossed`, `Fee`, `Trade ID`

The trades are merged with the corresponding day's sentiment classification, then aggregated to study PnL, win rate, and volume behavior across different sentiment regimes.

## Objectives

- Compare trader profitability (Closed PnL) across Fear vs Greed market conditions
- Compare win rates across sentiment regimes
- Analyze trading volume and position sizing behavior by sentiment
- Identify top and bottom performing accounts
- Visualize daily PnL against the Fear/Greed Index over time
- Derive actionable insights for trading strategy


## Data Access

The raw trader dataset (~3.4M rows) is too large to host on GitHub. To reproduce this analysis:

1. Download `historical_data.csv` from the source [Google Drive link] (or your own data source)
2. Place it in the `data/` folder locally, or in your Google Drive if running via Colab
3. Update the file paths in the notebook's "File Paths" cell accordingly

The sentiment dataset (`fear_greed_index.csv`) is small and included directly in `data/`.

## How to Run

### Option A: Google Colab (recommended)
1. Open `trader_sentiment_analysis.ipynb` in Google Colab
2. Mount Google Drive (cell provided) or upload files manually
3. Update `TRADER_FILE` and `SENTIMENT_FILE` paths
4. Run all cells (Runtime → Run all) — charts render inline as each cell executes

### Option B: Local Jupyter
```bash
pip install -r requirements.txt
jupyter notebook trader_sentiment_analysis.ipynb
```
Update the file paths at the top of the notebook to point to your local CSVs, then run all cells.

## Methodology

- The trader dataset is processed in chunks (200,000 rows at a time) to stay memory-safe given its size
- Each trade's `Timestamp IST` is converted to a date and merged with the corresponding day's Fear/Greed classification
- Daily, account-level, and sentiment-level aggregates are computed: total/average PnL, win rate, trading volume
- Results are visualized across 5 charts: PnL by sentiment, win rate by sentiment, PnL vs sentiment index over time, volume by sentiment, and top/bottom performing accounts

## Key Findings

*(To be filled in after running the notebook on the full dataset — summarize win rate differences, PnL patterns, and volume behavior across Fear vs Greed regimes here.)*

## Tech Stack

- Python, pandas, numpy
- matplotlib, seaborn for visualization
- Google Colab / Jupyter Notebook

## Author

Sayani Adak— B.Tech AI & ML, Adamas University
