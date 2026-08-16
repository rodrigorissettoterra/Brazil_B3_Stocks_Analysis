# Brazil B3 Stocks Analysis

> **Investment intelligence combining fundamental analysis, technical indicators, and a configurable ranking model for Brazilian stocks.**

A data-driven project designed to transform financial and market data from companies listed on **B3 — Brasil, Bolsa, Balcão** into a structured decision-support framework.

The project combines **fundamental analysis, technical indicators, normalization, weighted scoring, data automation, and interactive visualization** to support systematic stock comparison.

<p>
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?logo=googlecolab&logoColor=white" alt="Google Colab">
  <img src="https://img.shields.io/badge/Google%20Sheets-Data-34A853?logo=googlesheets&logoColor=white" alt="Google Sheets">
  <img src="https://img.shields.io/badge/Looker%20Studio-Dashboard-4285F4?logo=google&logoColor=white" alt="Looker Studio">
</p>

---

## The problem

Stock analysis rarely depends on a single metric. A company may present strong profitability and financial fundamentals while showing weak market momentum; another may display positive technical signals while carrying higher financial risk.

This project was designed around three practical questions:

> **Is this a good company?**  
> **Is this a good time to buy?**  
> **Which stocks best match a given analytical profile?**

Instead of relying on isolated indicators, the project combines multiple dimensions into a normalized and configurable scoring framework.

---

## Architecture

```text
Brazilian Stocks
       ↓
Data Collection
Fundamentus + yfinance
       ↓
Data Cleaning & Feature Engineering
       ↓
Fundamental Indicators + Technical Indicators
       ↓
Normalization (0 → 1)
       ↓
Component Scores
       ↓
Weighted Final Score
       ↓
Google Sheets
       ↓
Looker Studio
       ↓
Analysis & Ranking
```

The workflow separates **data collection, analytical transformation, scoring, and visualization**, making the logic easier to inspect and adjust.

---

## What this project demonstrates

- financial and market data collection;
- data cleaning and feature engineering;
- fundamental and technical analysis;
- indicator normalization;
- quantitative scoring;
- configurable weights;
- stock ranking;
- automated export to Google Sheets;
- interactive visualization with Looker Studio;
- business-oriented interpretation of quantitative signals.

---

## Fundamental analysis

The fundamental layer evaluates characteristics related to profitability, financial strength, growth, and market liquidity.

Indicators used in the project include:

- Price
- Dividend Yield
- ROIC
- ROE
- Net Margin
- Revenue Growth — 5 years
- Debt-to-Equity
- Current Ratio
- Average Daily Liquidity — 2 months

The objective is not to identify one universally superior indicator, but to combine several dimensions of company quality into a comparable analytical structure.

---

## Technical analysis

The technical layer represents recent market behavior, momentum, and trend.

Indicators include:

- RSI — 14 periods
- MACD Histogram
- 20-day Return
- Distance from the 200-day Moving Average
- Relative Volume

These signals complement the fundamental analysis rather than replacing it.

```text
Fundamentals → Company quality
Technical signals → Market behavior
           ↓
Combined analytical perspective
```

---

## Normalization

Financial indicators use different units, scales, and directions. To make them comparable, values are transformed to a common interval between `0` and `1`.

For variables where higher values are preferable:

```text
normalized_score = (x - min) / (max - min)
```

For variables where lower values are preferable:

```text
normalized_score = (max - x) / (max - min)
```

RSI uses a separate transformation:

```text
RSI_score = 1 - |RSI - 50| / 50
```

---

## Scoring model

### Quality Score

Represents company fundamentals using normalized profitability and financial-strength indicators.

### Technical Score

Represents momentum and market behavior using normalized technical indicators.

### Final Investment Score

The final score combines analytical components through configurable weights:

```text
Final Score =
    w1 × Quality Score
  + w2 × Technical Score
  + w3 × Dividend Score
  + w4 × Liquidity Score
```

with the weights summing to `1` and the final score constrained to the interval from `0` to `1`.

The weighting scheme can be adjusted according to the analytical profile being evaluated.

---

## Outputs

### Notebook

[View the analysis notebook](./Análise_Fundamentalista_e_Técnica.ipynb)

[Open the original Colab workflow](https://colab.research.google.com/drive/1MuqEMHkNBuEstzDJyjo-SQz4-licZQr3?usp=sharing)

### Google Sheets dataset

[View the processed analytical dataset](https://docs.google.com/spreadsheets/d/1GyMu7RiKHfbDA0Bio8VG8LjmX2aHlfy6BdE1GwRq4o8/edit?usp=sharing)

### Looker Studio dashboard

The dashboard contains three analytical views:

1. Fundamental Analysis
2. Technical Analysis
3. Investment Ranking

[Open the interactive dashboard](https://lookerstudio.google.com/reporting/a36fd4cc-992e-4b03-8f46-2bf03a9e20d2)

---

## Technology stack

| Layer | Technology |
|---|---|
| Programming | Python |
| Data manipulation | Pandas, NumPy |
| Fundamental data | Fundamentus |
| Market data | yfinance |
| Automation / export | gspread |
| Analytical storage | Google Sheets |
| Visualization | Looker Studio |
| Development | Jupyter Notebook / Google Colab |

---

## Analytical considerations

The ranking should be interpreted as a **decision-support model**, not as an objective measure of the intrinsic value of a company.

Results depend on:

- selected indicators;
- normalization rules;
- chosen weights;
- data quality;
- market conditions;
- time windows used for technical indicators.

Different investment philosophies may legitimately produce different rankings.

---

## Limitations

This project does not currently include:

- transaction costs or taxes;
- portfolio optimization;
- historical backtesting of the ranking strategy;
- survivorship-bias analysis;
- risk-adjusted portfolio metrics;
- automated production refresh;
- probabilistic forecasts.

The current objective is to demonstrate the transformation of heterogeneous financial signals into a structured analytical ranking system.

---

## Possible next steps

- automated daily refresh;
- historical backtesting;
- portfolio simulation;
- risk-adjusted performance metrics;
- optimization of scoring weights;
- Machine Learning for ranking;
- API-based serving;
- portfolio construction and rebalancing.

---

## Disclaimer

This project is intended for **educational, analytical, and portfolio purposes only**. The scores, rankings, indicators, and analyses presented here do not constitute financial advice, investment recommendations, or guarantees of future performance.

---

## Author

**Rodrigo Terra**

Data & AI professional with a multidisciplinary background in Data Science, Analytics Engineering, Artificial Intelligence, technology, and quantitative problem solving.

- GitHub: [Rodrigo Terra](https://github.com/rodrigorissettoterra)
- LinkedIn: [Rodrigo Terra](https://www.linkedin.com/in/rodrigo-rissetto-terra/)
