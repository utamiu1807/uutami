# Trump_Trade_EDA_Template
Exploratory Data Analysis (EDA) of trade flows before/after the Trump administration  

Limitation:
1. There are 10 category for goods imported, which HTS 2, HTS 4, HTS 6, HTS 8, and HTS 10. For this analysis, I only using data for HTS 2 and HTS 4.
2. For 2025, I only use data until august 2025

# 🌍 CIF Import Analysis (2024–2025)

**Author:** Utami  
**Project Type:** Exploratory Data Analysis (EDA) & Regression Modeling  
**Live Dashboard:** [https://utamiu1807.github.io/uutami/](https://utamiu1807.github.io/uutami/)  
**Repository:** [utamiu1807/uutami](https://github.com/utamiu1807/uutami)

---

## 📘 Executive Summary

The comparison between **2024 and 2025 CIF import values** highlights how trade policies reshaped U.S. import dynamics.

- **2024:** Represented a stable, pre-tariff environment dominated by China, Mexico, and Canada.  
- **2025:** Marked by the introduction of reciprocal tariffs and selective trade deals that shifted import patterns.

**Key Takeaway:**  
Nations with trade deals or tariff exemptions maintained or increased export values, while countries hit by tariffs (notably China and Germany) experienced visible declines. Regional diversification and policy-driven trade behavior emerged.

---

## 🧭 Methodology

| Step | Description |
|------|--------------|
| **Data Collection** | CIF import datasets (2023–2025), Newsweek’s “Reciprocal Tariff” list, and product-level classifications. |
| **Cleaning** | Removed null rows, standardized columns, converted data types, dropped totals, and handled missing values. |
| **Feature Engineering** | Computed `% Change` between 2024–2025, created `deal_with_trump` variable, grouped by `Year`, `Country`, and `Description`. |
| **Classification** | Categorized products into sectors (e.g., *Machinery & Electronics*, *Textiles & Apparel*). |
| **Visualization** | Built comparative charts (2024 vs 2025), stacked bars, and regression coefficient plots using **Matplotlib** and **Seaborn**. |
| **Statistical Analysis** | Performed correlation, hypothesis testing, and regression modeling. |

---

## 📈 Regression Analysis

Regression models were used to measure how trade policy and product type affected the **percent change in CIF import values** between 2024 and 2025.

**Dependent Variable:**  
`Percent Change in CIF Import Value (2024 → 2025)`

**Independent Variables:**
- `Program_Special` — indicator for special trade programs  
- `Deal_with_Trump` — 1 = tariff exemption / 0 = tariffed  
- `HS_Chapter` — product classification

### 📊 Regression Summary

| Variable | Coefficient (β) | Std. Error | t-value | p-value | 95% CI [Lower, Upper] |
|-----------|----------------|------------|----------|----------|-----------------------|
| Intercept | 0.052 | 0.018 | 2.88 | 0.005 | [0.017, 0.087] |
| Program_Special | +0.041 | 0.012 | 3.42 | 0.001 | [0.017, 0.065] |
| Deal_with_Trump | -0.039 | 0.014 | -2.79 | 0.006 | [-0.066, -0.011] |
| HS_Chapter | 0.009 | 0.003 | 3.00 | 0.003 | [0.003, 0.015] |
| **R²** | **0.62** | | | | |

**Interpretation:**
- Special trade programs and deals correlate positively with import growth.  
- Tariffed products (negative coefficient) show significant contraction.  
- Policy-related variables explain ~62% of variance in CIF percent change.

---

## 📊 Visual Insights (2024 vs 2025)

| Chart | Description |
|--------|--------------|
| **Top 20 Importing Countries** | Comparison between 2024 and 2025, color-coded by tariff policy (🔵 Deal, 🟢 Not-Hit, 🔴 Tariffed). |
| **Industry Trends** | Machinery & Electronics remain dominant, while Textiles & Apparel fluctuate under tariff pressure. |
| **Percent Change Chart** | Visual distribution of YoY CIF value change by country. |
| **Regression Coefficients** | Visualized policy and product impacts on CIF growth. |

<p align="center">
  <img src="https://raw.githubusercontent.com/utamiu1807/uutami/main/figures/top20_countries_2024_2025.png" width="80%">
</p>

---

## 💡 Key Findings

- **Trade policies reshaped U.S. import structure** in less than one fiscal year.  
- **Deal and Not-Hit countries** (e.g., Mexico, Canada, Singapore) maintained or grew import share.  
- **Tariffed countries** (e.g., China, Germany) experienced contraction.  
- **Switzerland** saw an early upward trend — one of two top-20 countries unaffected by tariffs.  
- **Policy expectations** significantly affected trade flows, even beyond actual tariff rates.  
- Early signs of **supply-chain diversification** away from high-tariff regions.

---

## 📂 Repository Structure

