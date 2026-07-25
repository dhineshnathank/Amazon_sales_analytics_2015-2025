# 🛒 Amazon India: A Decade of Sales Analytics 📈🇮🇳

End-to-end e-commerce analytics project on Amazon India's 10-year transactional dataset (2015–2025) — from messy raw data to a production-ready **Power BI dashboard suite** and **Python-based analytical deep dives**.

---

## 📌 Overview

This project builds a complete analytics pipeline on a ~1.13M-row, 37-column Amazon India e-commerce dataset:

- 🧹 Advanced data cleaning on realistic messy data (~25% intentional quality issues)
- 📊 Exploratory data analysis and statistical deep dives in Python
- 🗄️ SQL-backed cleaned dataset (`amazon_india_cleaned_data`) for BI connectivity
- 📈 Multi-page interactive **Power BI** dashboard suite for business decision-making

**Domain:** E-Commerce Analytics
**Tech Stack:** Python (Pandas, Matplotlib, Seaborn) · SQL · Power BI · DAX

---

## 🎯 Problem Statement

Amazon India generates massive volumes of transactional data with real-world quality issues — inconsistent formats, missing values, duplicates, and outliers. This project cleans that data, extracts business insights through exploratory analysis, and delivers a multi-page Power BI dashboard suite covering revenue, customers, delivery, payments, and strategic performance.

---

## 🗂️ Dataset

- **Transactions:** ~1,000,000 records spanning 2015–2025 (`amazon_india_{year}.csv`)
- **Product Catalog:** 2,000+ products (`amazon_india_products_catalog.csv`)
- **Coverage:** 30+ Indian cities (Metro to Rural), 8 major categories, 25+ subcategories, 100+ brands
- **Cleaned table:** `amazon_india_cleaned_data` — 1.13M rows, 37 columns

Key fields: `transaction_id`, `customer_id`, `product_id`, `order_date`, `category`/`subcategory`, `original_price_inr`, `discount_percent`, `final_amount_inr`, `customer_city`, `is_prime_member`, `payment_method`, `delivery_days`, `return_status`, `is_festival_sale`, `customer_spending_tier`.

---

## 🧹 Data Cleaning

Addressed real-world data quality issues including:

| Issue | Resolution |
|---|---|
| Mixed date formats & invalid dates | Standardized to `YYYY-MM-DD` |
| Price fields with ₹ symbols, commas, text | Converted to clean numeric INR |
| Inconsistent ratings (`4 stars`, `3/5`, etc.) | Standardized to 1.0–5.0 numeric scale |
| City name variants (Bangalore/Bengaluru) | Standardized geography |
| Mixed boolean formats (`Yes/No`, `1/0`, `Y/N`) | Unified to `True/False` |
| Category naming inconsistencies | Standardized taxonomy |
| Invalid/negative delivery days | Cleaned via `VALUE()` conversion, threshold checks |
| Duplicate transactions | Distinguished genuine bulk orders vs. data errors |
| Decimal-point price outliers | Corrected via statistical + domain checks |
| Payment method naming variants | Standardized categorical hierarchy |

---

## 📊 Python Analysis — Price vs. Demand

A dedicated Python (Jupyter/VS Code) analysis exploring pricing and demand relationships:

- Correlation matrices between price and demand
- Subcategory- and spending-tier-level breakdowns
- Festival vs. non-festival sales comparison
- Prime vs. non-Prime member segmentation
- Static `matplotlib` / `seaborn` visualizations throughout

---

## 📈 Power BI Dashboard Suite

A multi-page Power BI report built on `amazon_india_cleaned_data`:

1. **Executive Summary** — KPI cards, slicers, YoY growth, subcategory performance
2. **Strategic Overview** — Geographic map, custom `DateTable` time intelligence, MoM/QoQ/YoY growth measures, festival sale lift, discount-based profitability proxy
3. **Delivery Performance** — Custom `Is On Time` measure using per-delivery-type thresholds
4. **Payment Analytics** — Payment method trends and adoption patterns
5. **Return & Cancellation** — Return rate and reason analysis
6. **Customer Segmentation** — RFM analysis via a calculated `CustomerRFM` table, scoring, LTV tiers, and recommended actions
7. **Demographics & Behavior** — Subcategory preferences, rating patterns, revenue by customer spending tier

### Key DAX Measures
```dax
Total Orders = DISTINCTCOUNT(transaction_id)
Revenue = SUM(final_amount_inr)
Avg Discount % = AVERAGE(discount_percent)
Avg Customer Rating = AVERAGE(customer_rating)
```

All revenue figures are displayed in **₹ Crores (₹ Cr)** for executive readability.

---

## 🛠️ Setup

```bash
git clone <repo-url>
cd amazon-india-sales-analytics
pip install -r requirements.txt
```

**Requirements:** `pandas`, `matplotlib`, `seaborn`, `sqlalchemy`

Open `dashboard/amazon_india_dashboard.pbix` in Power BI Desktop and point the data source to your cleaned SQL table/CSV to refresh.

---

## 💡 Key Business Insights

- Revenue growth trends across the decade with clear festival-driven spikes
- Prime membership correlates with higher average order value and order frequency
- UPI adoption rose sharply while COD declined over the period
- Delivery performance varies meaningfully by city tier
- RFM segmentation surfaces high-value customer cohorts for targeted retention

---

## 📚 Skills Demonstrated

`Python` · `Pandas` · `Matplotlib` · `Seaborn` · `SQL` · `Power BI` · `DAX` · `Data Cleaning` · `Business Intelligence` · `Statistical Analysis`

