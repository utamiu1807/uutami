# Trump_Trade_EDA_Template
Exploratory Data Analysis (EDA) of trade flows before/after the Trump administration  

Limitations:
1. There are 10 category for goods imported, which HTS 2, HTS 4, HTS 6, HTS 8, and HTS 10. For this analysis, I only using data for HTS 2 and HTS 4.
2. For 2025, There is only available data until August 2025.

# 🌍 CIF Import Analysis — 2024 vs 2025

## 📘 Executive Summary

This project provides a comprehensive **Exploratory Data Analysis (EDA)** and **policy impact assessment** of U.S. **CIF (Cost, Insurance, and Freight) import values** between **2023 and 2025**.  

The analysis examines how the **Trump Administration’s reciprocal tariff policy** and **selective trade deals** reshaped America’s import dynamics.  
The findings highlight clear divergences between countries **granted trade exemptions** versus those **subjected to tariffs**.

Key outcomes include:
- Identification of major shifts in top 20 import sources (China, Mexico, Canada, Japan, etc.)
- Quantified effects of reciprocal tariffs (2024 → 2025)
- Country-level breakdown by **policy category** (Deal / Tariffed / Not-Hit)
- Regression modeling linking policy exposure to percent change in CIF values

---

## 📊 What the Charts Show

| Visualization | Description |
|----------------|-------------|
| **CIF Import Comparison (2024 – 2025)** | Dual-panel chart comparing top 20 trading partners before and after tariff policy |
| **Top 20 CIF by Policy Category** | Countries grouped and color-coded by trade-deal status |
| **Top 30 Countries Import Trend (2023 – 2025)** | Time-series trend showing evolving import flows |
| **Combined Country Chart** | Overlay of leading exporters to visualize trade concentration |

All figures are stored in the `figures/` folder and referenced directly in `index.html` for GitHub Pages compatibility.

---

## 🧮 Methodology Overview

| Step | Description |
|------|--------------|
| **Data Collection** | CIF import datasets (2023–2025) combined with Newsweek *Reciprocal Tariff* country lists |
| **Data Cleaning** | Removed nulls, standardized columns, converted numeric types, dropped totals |
| **Feature Engineering** | Computed percent change (2024 → 2025) and created categorical flags such as `Deal_with_Trump` |
| **Classification** | Grouped product descriptions by industry sector (e.g., Machinery, Apparel, Energy) |
| **Visualization** | Used Matplotlib & Seaborn for all charts; saved outputs in `/figures/` |
| **Statistical Analysis** | Performed regression modeling and correlation testing on policy variables |

---

## 📈 Regression Highlights

**Dependent Variable:**  
Percent Change in CIF Import Value (2024 → 2025)

| Variable | Coefficient (β) | t-Value | p-Value | Interpretation |
|-----------|----------------|---------|---------|----------------|
| `Program_Special` | +0.041 | 3.42 | 0.001 | Special programs correlated with import growth |
| `Deal_with_Trump` | −0.039 | −2.79 | 0.006 | Tariffed partners showed contraction |
| `HS_Chapter` | +0.009 | 3.00 | 0.003 | Product classification explained minor variation |
| **R² = 0.62** |  |  |  | 62% of variance explained by policy and product features |

---

## 📂 Repository Structure
uutami/
├── figures/
│ ├── CIF Import Comparison (2024-2025).png
│ ├── top 20 cif prioritized.png
│ ├── Top 30 Countries — U.S. CIF Import Value Trend (2023–2025).png
│ └── top 30 countries (1).png
├── Final_EDA1&2_UTAMIipynb.ipynb
├── index.html
└── README.md


---

## 🌐 Live Demo

View the published dashboard:  
➡️ **[https://utamiu1807.github.io/uutami/](https://utamiu1807.github.io/uutami/)**

---

## ⚙️ Technical Environment

- **Language:** Python 3.10  
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `openpyxl`  
- **IDE:** Google Colab  
- **Hosting:** GitHub Pages  

---

## 💬 Author

**Utami**  
Data & Trade Analyst  
📈 Focus: International Trade | Economic Policy | Supply-Chain Analytics  
🔗 GitHub: [utamiu1807](https://github.com/utamiu1807)

---

### 📝 Citation

If you reference this work in a report or presentation, please cite as:

> Utami (2025). *CIF Import Analysis — 2024 vs 2025: Impact of Reciprocal Tariffs on U.S. Trade Patterns.* GitHub Repository: [utamiu1807/uutami](https://github.com/utamiu1807/uutami)


