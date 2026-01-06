# Sales Performance Analysis & Revenue Forecasting (Retail Case Study)

## Overview

This project analyses 12 months of retail sales data (≈185k transactions) to understand
what drives revenue and to build a simple, transparent forecasting approach for a
mid-size retailer. The focus is on identifying high-value products, understanding
pricing behaviour, and uncovering time patterns that can inform promotions,
staffing and inventory decisions.

Although the dataset is based on the well-known **Superstore** sample, it is treated
here as a proxy for a real client: a retail business looking for clear, data-backed
answers to commercial questions.

---

## Business Context & Key Questions

From the perspective of a **Head of Sales / Commercial Manager**, this analysis is
designed to answer:

1. **Which products and categories drive most of our revenue and margin?**  
2. **How do price and discounting affect demand?** Are there price points where
   elasticity changes noticeably?
3. **When do we actually sell the most?** (days of the week, times of day,
   seasonality over the year)
4. **What can we reasonably expect future sales to look like**, assuming no major
   structural changes?
5. **Which commercial levers should we pull** (promotions, pricing, assortment,
   inventory focus) to improve performance?

---

## Data

- **Source:** Superstore-style transactional dataset (orders, customers, products,
  categories, regions, order dates, quantities, revenue, discounts).
- **Grain:** One row per order line.
- **Time horizon:** ~12 months of data.
- **Size:** ≈185,000 rows after basic cleaning and filtering.

Key fields used:

- `Order Date`, `Ship Date`
- `Product ID`, `Product Name`, `Category`, `Sub-Category`
- `Region`, `City`, `Customer Segment`
- `Sales`, `Quantity`, `Discount`, `Profit`

---

## Approach

The project is implemented in Python using Jupyter Notebooks and follows a
business-first workflow:

1. **Data Cleaning & Preparation**
   - Handle missing values and data types.
   - Create derived variables (e.g. gross revenue, weekday/weekend flags,
     hour-of-day buckets).
   - Ensure consistent date/time handling.

2. **Descriptive & Diagnostic Analysis**
   - Basic KPIs: total revenue, orders, units, average basket size.
   - Revenue/margin breakdown by:
     - Product, Sub-category, Category
     - Region and Customer Segment
   - **Pareto analysis** to identify the small set of products generating the
     majority of revenue.

3. **Pricing & Discount Behaviour**
   - Explore distribution of prices and discounts.
   - Identify **price bands / discount bands** where demand behaves differently.
   - Examine how heavy discounting interacts with margin and volume.

4. **Time-Based Patterns**
   - Daily and weekly seasonality (day of week, week of year).
   - Hour-of-day patterns to understand when customers actually buy.
   - Identify peaks such as **mid-week (Tue–Thu) daytime** sales concentration.

5. **Simple Time-Series Forecasting**
   - Aggregate sales to a regular time-series (e.g. daily/weekly revenue).
   - Fit baseline forecasting models (e.g. moving average, naïve, simple
     time-series models).
   - Compare forecast performance and produce short-term projections.

6. **Recommendations**
   - Translate analytical findings into concrete actions across promotions,
     assortment and inventory planning.

---

## Repository Structure

_Currently:_

- `Sample - Superstore.csv` – transactional sales dataset.   
- `sales analysis.ipynb` – main notebook with sales performance analysis and visualisations.
- `.ipynb_checkpoints/` – automatic Jupyter checkpoints (can be ignored in Git).

---

## Tools & Libraries

- **Language:** Python 3.x
- **Core libraries:**
  - `pandas` – data wrangling and aggregation
  - `numpy` – numerical operations
  - `matplotlib`, `seaborn` – visualisation
  - `datetime` / `dateutil` – date/time handling
- **Environment:** Jupyter Notebook

---

## How to Run the Analysis

1. Clone the repository:

   ```bash
   git clone https://github.com/Kimuyu-Charles/Sales-Analysis.git
   cd Sales-Analysis
