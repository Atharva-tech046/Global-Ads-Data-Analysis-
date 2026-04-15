# 📊 Programmatic Ad-Tech Yield Engine

## 🎯 Objective
Built an executive-grade Power BI dashboard to analyze global digital marketing performance, simulating the real-time reporting environment of a programmatic ad-network. The goal was to track campaign efficiency and identify high-yield advertising segments across multiple platforms (Google Ads, TikTok Ads, Meta Ads).

## 🛠️ Technical Architecture
* **ETL & Data Cleaning:** Utilized **Power Query** to extract, clean, and transform raw ad-server logs. Removed static, pre-calculated averages to prevent mathematical aggregation errors.
* **Data Modeling:** Engineered a **Star Schema** relational model, optimizing query performance by filtering a heavy central `Fact_Table` through lightweight dimensional slicers.
* **DAX Engineering:** Wrote custom DAX measures using `DIVIDE(SUM())` logic to dynamically calculate core ad-tech KPIs based on real-time stakeholder filtering.

## 🧮 Core DAX Measures Engineered
Instead of relying on flat file averages, the engine dynamically calculates:
* **ROAS (Return on Ad Spend):** `DIVIDE(SUM(Fact_Table[revenue]), SUM(Fact_Table[ad_spend]), 0)`
* **CPC (Cost Per Click):** `DIVIDE(SUM(Fact_Table[ad_spend]), SUM(Fact_Table[clicks]), 0)`
* **CTR (Click-Through Rate):** `DIVIDE(SUM(Fact_Table[clicks]), SUM(Fact_Table[impressions]), 0)`

## 📈 Executive UI & Insights
Designed a **Dark Mode Executive Interface** optimized for high-level decision-making. 
* **Dynamic Slicing:** Users can isolate performance by Platform or Date.
* **Yield Matrix:** Utilizes conditional formatting to instantly highlight campaign types generating positive ROAS vs. those burning ad spend.
* **Spend vs. Revenue Tracking:** Visualizes the direct correlation between daily ad-budget pacing and revenue generation.

---
*Built as a portfolio project to demonstrate proficiency in Data Modeling, DAX, and Ad-Tech Commercial Metrics.*
