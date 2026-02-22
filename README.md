# Brazil B3 Stocks Analysis
## Fundamental &amp; Technical Analysis

B3 Investment Intelligence Dashboard

A data-driven investment dashboard integrating fundamental analysis,
technical analysis, and a custom weighted ranking system for the
Brazilian stock market (B3).

------------------------------------------------------------------------

Project Objective

This project was developed to answer three key investment questions:

1.  Is this a good company?
2.  Is this a good time to buy?
3.  Which stocks best fit my investment profile?

The solution integrates financial fundamentals, technical indicators,
and customizable weights into a structured scoring system ranging from 0
to 1.

------------------------------------------------------------------------

Architecture Overview

Data Collection (Python / Colab) ↓ Indicator Calculation ↓ Normalization
(0–1 scaling) ↓ Export to Google Sheets ↓ Visualization & Scoring
(Looker Studio)

------------------------------------------------------------------------

Step 1 – Data Collection & Processing (Google Colab)

Notebook:
https://colab.research.google.com/drive/1MuqEMHkNBuEstzDJyjo-SQz4-licZQr3?usp=sharing

Technologies Used: - Python - Fundamentus - yfinance - pandas - numpy -
gspread

Fundamental Indicators: - price - dividend_yield - roic - roe -
net_margin - revenue_growth_5y - debt_to_equity - current_ratio -
avg_daily_liquidity_2m

Technical Indicators: - rsi_14 - macd_hist - ret_20d - dist_sma_200 -
vol_rel

------------------------------------------------------------------------

Step 2 – Data Normalization

Positive Indicators (Higher = Better): (x - min) / (max - min)

Risk Indicators (Lower = Better): (max - x) / (max - min)

RSI Adjustment: 1 - ABS(RSI - 50) / 50

------------------------------------------------------------------------

Scoring Models

Quality Score: Average of normalized profitability and financial
strength metrics.

Technical Score: Average of normalized momentum and trend metrics.

Final Investment Score: Weighted average of Quality, Technical,
Dividend, and Liquidity components. Always constrained between 0 and 1.

------------------------------------------------------------------------

Google Sheets Dataset

https://docs.google.com/spreadsheets/d/1GyMu7RiKHfbDA0Bio8VG8LjmX2aHlfy6BdE1GwRq4o8/edit?usp=sharing

------------------------------------------------------------------------

Looker Studio Dashboard

https://lookerstudio.google.com/reporting/a36fd4cc-992e-4b03-8f46-2bf03a9e20d2

Pages: 1. Fundamental Analysis 2. Technical Analysis 3. Investment
Ranking

------------------------------------------------------------------------

Future Improvements

-   Automated daily refresh
-   Backtesting engine
-   Machine learning for weight optimization
-   API deployment
-   Portfolio simulation module

------------------------------------------------------------------------

Conclusion

This project demonstrates how quantitative methods can transform raw
financial data into structured analysis, objective scoring, and
interactive investment insights.
