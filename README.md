# 📊 India CPI Inflation Analysis (2013–2023) — Excel Data Analytics Project

> A comprehensive economic data analytics project analyzing **10 years of India's Consumer Price Index (CPI)** across **27 commodity categories**, **3 sectors (Rural, Urban, Rural+Urban)**, and **8 consolidated spending buckets** — built entirely in Microsoft Excel to uncover inflation trends, sectoral disparities, COVID-19 economic impact, and category-level price pressures driving household burden in India.

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Domain](https://img.shields.io/badge/Domain-Economic%20Analytics-blue?style=for-the-badge)
![Data](https://img.shields.io/badge/Data-CPI%20%7C%202013--2023-orange?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-377%20Monthly%20Observations-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Objectives of Analysis](#-objectives-of-analysis)
- [Dataset Description](#-dataset-description)
- [Methodology](#-methodology)
- [Dashboard Preview](#-dashboard-preview)
- [Key KPIs](#-key-kpis)
- [Key Insights & Economic Interpretation](#-key-insights--economic-interpretation)
- [Tools & Technologies](#️-tools--technologies)
- [Dashboard Features](#-dashboard-features)
- [How to Use](#-how-to-use)
- [Author](#-author)

---

## 🌐 Project Overview

India's Consumer Price Index (CPI) is the primary barometer of retail inflation — directly influencing the Reserve Bank of India's (RBI) monetary policy decisions, household purchasing power, and the lived economic reality of 1.4 billion citizens. A sustained CPI above the RBI's tolerance band of **4% ± 2%** triggers interest rate interventions that affect home loans, business credit, and consumer spending nationwide.

This project analyzes **all-India CPI data from January 2013 to April 2023** — a decade that encompassed demonetization (2016), the GST rollout (2017), a global pandemic (2020), the Russia-Ukraine supply shock (2022), and a post-pandemic normalization phase (2023). By dissecting inflation trends across 27 sub-categories and 8 consolidated buckets, this analysis provides the economic context behind the numbers that shape India's monetary policy.

---

## ❓ Problem Statement

India's inflation data is published by the Ministry of Statistics (MoSPI) in disaggregated form — making it difficult for analysts, policymakers, and citizens to answer fundamental questions:

- **Which categories are driving inflation above the RBI's 6% tolerance ceiling?**
- **Are rural households experiencing more inflation than urban households?**
- **How did the COVID-19 pandemic structurally shift India's inflation profile?**
- **Which commodity sectors are most volatile and most at-risk for future price shocks?**
- **Is food inflation consistently higher than headline CPI, and by how much?**

This project transforms 10 years of raw MoSPI CPI tables into a structured, analyzable dataset with clear answers to each of these questions.

---

## 🎯 Objectives of Analysis

| # | Objective | Analytical Approach |
|---|---|---|
| 1 | Profile the CPI basket composition across 8 spending buckets | Category weightage analysis using Pivot Tables |
| 2 | Measure year-over-year (YoY) inflation rate from January to December for each year | January–December CPI differential calculation |
| 3 | Track month-on-month (MoM) food inflation trends post-2022 supply shock | MoM % change calculation on Food & Beverages index |
| 4 | Compare inflation trajectories before and after COVID-19 (March 2020 divide) | Pre/Post Covid segmentation with timeline analysis |
| 5 | Correlate crude oil price movements with CPI inflation trajectory | Crude oil vs. CPI overlay analysis (2021–2023) |

---

## 🗂️ Dataset Description

**Source:** Ministry of Statistics and Programme Implementation (MoSPI), Government of India
**Period:** January 2013 – April 2023 | **Frequency:** Monthly
**Sectors:** Rural | Urban | Rural+Urban (Combined National)

### Schema — Original Data (377 rows × 30 columns)

| Column | Description | Type |
|---|---|---|
| `Sector` | Rural / Urban / Rural+Urban | Categorical |
| `Year` | Calendar year (2013–2023) | Integer |
| `Month` | Month of observation | Categorical |
| `Cereals and products` | CPI index for cereals sub-category | Float |
| `Meat and fish` | CPI index for protein foods | Float |
| `Egg` | CPI index for eggs | Float |
| `Milk and products` | CPI index for dairy | Float |
| `Oils and fats` | CPI index for edible oils | Float |
| `Fruits` | CPI index for fruits | Float |
| `Vegetables` | CPI index for vegetables | Float |
| `Pulses and products` | CPI index for lentils/pulses | Float |
| `Sugar and Confectionery` | CPI index for sugar | Float |
| `Spices` | CPI index for spices | Float |
| `Food and beverages` | Aggregate food sub-index | Float |
| `Clothing` | CPI index for clothing | Float |
| `Housing` | CPI index for housing | Float |
| `Fuel and light` | CPI index for fuel/energy | Float |
| `Health` | CPI index for healthcare | Float |
| `Education` | CPI index for education | Float |
| `Transport and communication` | CPI index for transport | Float |
| `General index` | **Headline CPI — the primary KPI** | Float |

### Consolidated Buckets (8 Spending Categories)

| Bucket | Sub-categories Included |
|---|---|
| **Food & Beverages** | Cereals, Meat, Egg, Dairy, Oils, Fruits, Vegetables, Pulses, Sugar, Spices, Prepared meals |
| **Energy** | Fuel and light |
| **Transportation** | Transport and communication |
| **Education** | Education |
| **Health & Personal Care** | Health, Personal care and effects |
| **Housing & Household** | Housing, Household goods and services |
| **Clothing & Footwear** | Clothing, Footwear |
| **Recreation & Miscellaneous** | Pan/tobacco, Recreation, Miscellaneous |

### Data Quality Notes
- **377 total observations** in original data | **372 rows** after cleaning
- **Missing values:** Rural Housing data missing for some months in 2013 (filled using Rural+Urban interpolation during cleaning)
- **Base year:** 2012 = 100 (all index values are relative to this base)

---

## 🔧 Methodology

The analysis followed a structured five-step workflow entirely within Microsoft Excel:

```
Step 1: Data Cleaning (Working Data sheet)
   └── Removed inconsistencies in Year column (float → integer)
   └── Handled 5 missing Rural Housing values via linear interpolation
   └── Standardized month naming conventions

Step 2: Category Consolidation (Buckets sheet)
   └── 27 sub-categories → 8 macro spending buckets
   └── Created weighted composite indices for each bucket
   └── Mapped sub-categories per the MoSPI classification scheme

Step 3: KPI Calculations (Problem Statement sheets 1–5)
   └── PS1: Bucket-level composition weightage (% share of basket)
   └── PS2: Year-on-year inflation rate (January vs. December each year)
   └── PS3: Month-on-month Food & Beverages inflation (Jun 2022–Apr 2023)
   └── PS4: Pre-COVID vs. Post-COVID inflation comparison (Food, Health, Essentials)
   └── PS5: Crude oil price vs. CPI correlation analysis (2021–2023)

Step 4: Visualization
   └── Line charts for CPI trend over time
   └── Bar/column charts for category comparison
   └── Pivot tables for sector-wise breakdowns
   └── Dashboard assembly with slicers

Step 5: Insight Synthesis
   └── Economic interpretation of each calculated metric
   └── Policy implications framed around RBI mandate
```

---

## 📊 Dashboard Preview

![India CPI Inflation Dashboard](./images/Dashboard_Screenshot.png)

---

## 📈 Key KPIs

| KPI | Value | Period |
|---|---|---|
| 📊 General CPI (Start) | **104.6** | January 2013 |
| 📊 General CPI (End) | **179.1** | May 2023 |
| 📈 Total CPI Growth | **+71.2%** | 10-year cumulative |
| 🔴 Peak YoY Inflation Rate | **6.65%** | 2014 |
| 🟡 Lowest YoY Inflation Rate | **3.18%** | 2023 (Jan–Apr) |
| 🍎 Food vs. General Gap (Peak) | **+5.27 index points** | 2016 |
| 🏘️ Rural–Urban CPI Gap (Peak) | **+4.61 points** | 2017 |
| ⛽ Fuel CPI (2022 Peak) | **182.0** | December 2022 |
| 🥦 Vegetables Std. Deviation | **25.32** | Most volatile category |
| 🌾 Food & Beverages Weight | **49.56%** | Of total CPI basket |

---

## 💡 Key Insights & Economic Interpretation

### 🔴 INSIGHT 1 — India's CPI Grew 71.2% in 10 Years, but the Rate Is Decelerating

The General CPI rose from **104.6 in January 2013 to 179.1 in May 2023** — a cumulative increase of 71.2%. However, the annual inflation rate has been decelerating: from a peak of **6.65% YoY in 2014** down to **3.18% in early 2023**. The key exception was 2022 (**6.62% YoY**), when Russia's invasion of Ukraine triggered global commodity price shocks that temporarily reversed the downward trend.

**Economic interpretation:** The long-run deceleration reflects the RBI's increasingly effective inflation targeting framework (adopted in 2016), supply-side reforms, and improved food distribution infrastructure. The 2022 spike was an external supply shock — not a structural domestic failure — as evidenced by its rapid correction in 2023.

---

### 🔴 INSIGHT 2 — Food Inflation Consistently Outpaces Headline CPI, Placing Disproportionate Burden on Low-Income Households

The **Food & Beverages bucket constitutes 49.56% of the CPI basket** — the single largest spending category for Indian households. Food inflation exceeded the General CPI in every year from 2013 to 2021, with the gap peaking at **+5.27 index points in 2016**. Only in 2023 did food inflation fall below headline CPI for the first time in the dataset.

**Vegetables are the single most volatile CPI sub-category** with a standard deviation of **25.32** — nearly 5× more volatile than the General index (std: 20.27). Vegetable CPI reached **230.5 in December 2020** — a 130% increase over the base year — driven by pandemic-related supply chain disruptions.

**Economic interpretation:** When food inflation persistently exceeds headline CPI, it constitutes a regressive tax — lower-income households who spend a higher proportion of income on food bear a disproportionately large inflation burden. This is a distributional equity issue, not just a macroeconomic one.

---

### 🟡 INSIGHT 3 — COVID-19 Created a Structural Break in India's Inflation Trajectory

A before/after analysis using **March 2020 as the structural break point** reveals:

| Metric | Pre-COVID (Jan 2019–Feb 2020) | Post-COVID (Apr 2020–Apr 2023) |
|---|---|---|
| Avg Food & Beverages Index | ~1,850 | ~2,050+ |
| Food MoM Inflation | Mild (0–2%) | Elevated and volatile |
| Health & Personal Care Index | ~290 | Rising sharply |
| Essentials (Fuel, Clothing) | Stable | Structural upward shift |

Post-March 2020, food inflation became more volatile, Health index rose sharply (reflecting pandemic-driven healthcare demand), and the General CPI entered a new, higher trajectory. **The CPI never returned to its pre-COVID growth rate** — confirming a permanent level shift, not a temporary spike.

**Economic interpretation:** This mirrors the global "K-shaped recovery" phenomenon — where pandemic disruptions permanently repriced essential goods, hitting consumption-heavy households hardest while asset-owners recovered faster.

---

### 🟡 INSIGHT 4 — Fuel Inflation Overtook General CPI in 2022, Signalling the Russia-Ukraine Supply Shock

In 2022, **Fuel & Light CPI crossed above General CPI for the first time** — reaching **182.0 by December 2022** vs. a General CPI of 175.7. The divergence began sharply in **April 2022** (Fuel: 172.2 vs. General: 170.1) and widened consistently through year-end.

This coincides precisely with Russia's invasion of Ukraine in February 2022 and the resulting global crude oil and natural gas price spike. The crude oil correlation data (Problem Statement 5) confirms that **crude oil prices peaked at ₹9,119.55/barrel in June 2022**, corresponding to Fuel CPI of 176.0.

**Economic interpretation:** Energy inflation is particularly damaging because it is non-discretionary and cascades into transportation and food prices (through higher logistics costs). The RBI responded with multiple repo rate hikes through 2022 — directly traceable to this fuel-driven CPI breach of the 6% tolerance ceiling.

---

### 🟢 INSIGHT 5 — Rural India Consistently Experiences Higher Inflation Than Urban India, With the Gap Peaking in 2017

Rural CPI exceeded Urban CPI in every year from 2013 to 2023, with the gap peaking at **4.61 index points in 2017** and narrowing to **1.86 points in 2023**. The 2017 peak aligns with the post-demonetization (November 2016) disruption period, where rural cash-dependent supply chains were disproportionately disrupted, causing localized food price spikes in rural markets.

**Economic interpretation:** The persistent rural CPI premium reflects structural inefficiencies in rural supply chains, higher dependence on locally produced food (which has greater price volatility), and limited access to the price-moderating effects of modern retail infrastructure available in urban centers. Narrowing this gap is a key rural development policy objective.

---

### 🟢 INSIGHT 6 — Seasonal Pattern: October–November Is India's Highest-Inflation Window

Analyzing monthly CPI averages across all 11 years reveals a clear seasonal pattern:

| Season | Avg General CPI | Driver |
|---|---|---|
| Oct–Nov | **141.9–142.3** (highest) | Post-monsoon vegetable supply lag; festival demand surge |
| May–Jun | **140.4–137.8** | Pre-harvest season; summer heat impact on perishables |
| Jan–Feb | **138.2** (lowest) | Post-harvest abundance; seasonal food price correction |

**Economic interpretation:** India's inflation has an embedded agricultural calendar. The Oct–Nov inflation window reflects the lag between the monsoon harvest and market supply — a structural feature that the RBI's monetary policy tools cannot easily address, since interest rate hikes cannot fix weather-dependent supply constraints.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Complete end-to-end analysis — data cleaning, transformation, calculations, visualization, and dashboard |
| **Pivot Tables** | Category aggregation, sector-wise breakdowns, YoY/MoM analysis |
| **Excel Formulas** | `AVERAGEIFS`, `SUMIFS`, `IFERROR`, `IF`, `TEXT`, `VLOOKUP` for KPI calculations |
| **Excel Charts** | Line charts (trend), column charts (comparison), area charts (composition) |
| **Conditional Formatting** | Heat maps for category-level index comparison |
| **Slicers** | Interactive filtering by year, sector, and category |

**Why Excel?** CPI analysis in Excel demonstrates a critical analyst skill: deriving institutional-grade economic insights from structured government data without requiring specialized statistical software — directly applicable in policy research, consulting, and banking roles.

---

## ✨ Dashboard Features

| Feature | Description |
|---|---|
| **Headline CPI Trend Line** | 10-year General Index trend for Rural, Urban, and Combined sectors |
| **YoY Inflation Rate Chart** | Annual inflation rate (2014–2023) with RBI 4% target and 6% ceiling reference lines |
| **Category Composition Chart** | Basket weightage by 8 spending buckets (Food dominates at 49.56%) |
| **Food vs. General CPI Overlay** | Gap analysis showing persistent food inflation premium over headline CPI |
| **Sector Comparison (Rural vs. Urban)** | Year-wise Rural–Urban CPI differential trend |
| **Pre/Post COVID Timeline** | Inflation trajectory with March 2020 structural break marker |
| **Crude Oil vs. Inflation Correlation** | 2021–2023 overlay chart linking global oil prices to domestic CPI |
| **Seasonal Pattern Chart** | Month-wise average CPI showing Oct–Nov peak pattern |
| **MoM Food Inflation Tracker** | Month-on-month food price change chart (H2 2022 – H1 2023) |
| **Interactive Slicers** | Filter by Year, Sector (Rural/Urban/Combined), and Category Bucket |

---

## 🚀 How to Use

### For Recruiters & Viewers
1. **View the dashboard screenshot** in the `images/` folder above for an instant visual overview
2. **Open the Excel workbook** in `excel/` — all analysis, formulas, and charts are contained within
3. Navigate through the 9 sheets:
   - `Objective` → Project scope and category mapping
   - `Original Data` → Raw MoSPI CPI data (377 rows)
   - `Working Data` → Cleaned dataset
   - `Buckets` → 8-category consolidated view
   - `Problem statement 1–5` → Five analytical deep-dives
4. Use slicers on the dashboard to filter by Year, Sector, and Category

**Minimum Excel version:** Excel 2016+ (for slicer and modern chart compatibility)

---

## 📄 License

This project is licensed under the MIT License. CPI data is sourced from MoSPI, Government of India — publicly available for research and educational use.

---

## 👤 Author

**ARSHAD K I SHAIKH**
*Data Analyst | Economic Analytics | Excel · SQL · Power BI*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/arshadkishaikh)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/Arshadkishaikh)


---

> 💼 *This project demonstrates analytical depth on real government macroeconomic data — covering data cleaning, multi-dimensional categorization, time-series KPI calculation, pre/post event comparison, and external factor correlation — all delivered through Excel as the sole tool, reflecting practical skills directly applicable in consulting, banking, and policy research roles.*

> ⭐ If this project helped or inspired you, please give it a star!
