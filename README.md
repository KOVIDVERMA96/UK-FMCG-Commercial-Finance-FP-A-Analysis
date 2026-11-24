# UK FMCG Commercial Finance & FP&A Analysis

An end-to-end commercial finance portfolio project modeling marginal P&L performance, standard vs. actual cost variances, seasonality dynamics, and customer-level logistics profitability across UK grocery channels.

## Project Overview

This repository simulates a real-world fresh produce / perishable FMCG FP&A workflow—moving from raw ERP-style sales and cost exports to executive-ready BI reporting and commercial commentary.

The project is structured in two progressive phases:
1. **Phase 1 — Core Marginal P&L & Variance Analysis (`FMCG_2Month_Margin_Variance_Dataset.xlsx`)**
   * **Scope:** 2-month SKU-level dataset (July–August 2027, 4 SKUs).
   * **Focus:** Architecting a clean left-to-right marginal P&L (Gross Sales → Trade Discounts → Net Revenue → Actual Cost → True Gross Margin %), enforcing revenue-weighted margins over simple averages, and flagging adverse cost variances (`(Standard Cost - Actual Cost) × Units Sold`).
   * **Headline Results:** £253,600 Net Revenue | 40.9% Revenue-Weighted Gross Margin | -£6,950 Total Cost Variance.

2. **Phase 2 — "Depth & Width" Commercial Profitability (`FMCG_5Month_Commercial_FPnA_Dataset.xlsx`)**
   * **Scope:** 5-month multi-customer dataset (April–August 2027, 5 SKUs across Tesco, Sainsbury's, and Waitrose).
   * **Focus:** Expanding analysis across **Depth** (multi-month seasonality and yield trends) and **Width** (customer trade spend and route-to-market logistics costs).
   * **Headline Results:** £1,330,818 Total Net Revenue | 30.7% True Margin % | -£4,663 Total Cost Variance.

## Key Commercial Insights

* **Customer Profitability ("Width"):** While Tesco drives 51.9% of Net Revenue (£691,080), it absorbs £116,259 in trade discounts. Conversely, Waitrose delivers a higher True Margin (36.7% vs. Tesco's 28.9%) despite higher relative logistics intensity (9.0% of net revenue vs. 8.1% at Tesco).
* **The Seasonality Trap:** `SKU-C (Strawberries)` demonstrates perishable yield volatility—generating a +£10,150 favorable cost variance during peak June harvest before swinging to a -£20,414 adverse variance in August as end-of-season yields tighten.
* **Operational Cost Leaks:** `SKU-A (Apples)` accumulates a -£9,322 adverse cost variance over five months (driven heavily by an August supplier/cost spike of -£8,711), flagging an immediate procurement and warehouse investigation without prematurely delisting a core footfall driver.
* **The NPD Launch Trap:** `SKU-PREMIUM (Exotic)` launches in August with an impressive 60%+ gross margin and favorable variance. Commercially, month-one performance is treated as an outlier driven by initial pipeline fill and launch hype rather than a baseline for Q4 forecasting until 90-day repeat purchase rates stabilize.

## Repository Contents

* `FMCG_2Month_Margin_Variance_Dataset.xlsx` — Phase 1 raw SKU-level sales and cost variance dataset.
* `FMCG_5Month_Commercial_FPnA_Dataset.xlsx` — Phase 2 expanded 5-month dataset with customer, category, and per-unit logistics dimensions.
* Interactive Executive Dashboard — Built to visualize KPI headlines, revenue-weighted gross margins, customer profitability, and conditional-formatted SKU-by-month cost variance matrices.

## Core Financial Logic

* **Net Revenue** = `(Units Sold × Selling Price) - Trade Discount`
* **Gross Margin %** = `(Net Revenue - Total Actual Cost) / Net Revenue` *(revenue-weighted)*
* **Cost Variance (£)** = `(Standard Cost per Unit - Actual Cost per Unit) × Units Sold` *(negative = adverse cash impact; positive = favorable)*
