# Brazil B3 Stocks Analysis

> **Investment intelligence combining fundamental analysis, technical indicators, and a configurable ranking model for Brazilian stocks.**

A data-driven project designed to transform market and company fundamentals into a structured decision-support workflow for stocks listed on **B3 — Brasil, Bolsa, Balcão**.

The project combines financial fundamentals, technical market indicators, normalization techniques, and weighted scoring to help compare companies using a consistent analytical framework.

<p>
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Google%20Sheets-Data-34A853?logo=googlesheets&logoColor=white" alt="Google Sheets">
  <img src="https://img.shields.io/badge/Looker%20Studio-Dashboard-4285F4?logo=google&logoColor=white" alt="Looker Studio">
</p>

---

## The problem

Investment analysis usually combines different perspectives.

A company may have strong fundamentals but poor market momentum.

Another may show positive technical signals while presenting weak financial quality.

This project was designed around three questions:

> **Is this a good company?**

> **Is this a good time to buy?**

> **Which stocks best match the analytical criteria defined by the user?**

Instead of relying on one indicator, the project combines multiple signals into a normalized scoring framework.

---

## Architecture

```text
Brazilian Stocks
      ↓
Data Collection
Fundamentus + yfinance
      ↓
Data Cleaning
      ↓
Fundamental Indicators
      +
Technical Indicators
      ↓
Normalization
0 → 1
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
