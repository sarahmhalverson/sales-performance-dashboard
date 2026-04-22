# Sales Performance Dashboard

> End-to-end Power BI dashboard connected to a live PostgreSQL database — KPI tracking, regional breakdowns, and 12-month trend analysis demonstrating a full BI development workflow.

---

## 📋 Overview

A business intelligence dashboard built to demonstrate a complete data analyst workflow — from raw data in a PostgreSQL database through SQL queries and data modeling to a published, interactive Power BI report.

The dashboard provides executive-level visibility into sales performance with dynamic filtering, regional comparisons, and trend analysis over time.

---

## ✨ Features

- **KPI cards** — at-a-glance revenue, units sold, average order value, and growth rate metrics
- **Regional breakdown** — bar and map visuals comparing performance across regions and territories
- **12-month trend analysis** — line chart tracking revenue and volume over time with month-over-month comparison
- **Interactive slicers** — filter the entire dashboard by region, product category, and time period in one click
- **DAX measures** — custom calculations for YoY growth, running totals, and rolling averages
- **Live PostgreSQL connection** — dashboard pulls directly from a PostgreSQL database, not a static CSV

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| BI & Visualization | Microsoft Power BI Desktop |
| Database | PostgreSQL |
| Query Language | SQL |
| Data Modeling | Power BI Data Model, DAX |
| Publishing | Power BI Service (free tier) |

---

## 🗄 Database Schema

```sql
-- Core tables used in this dashboard
sales_orders      -- order ID, date, region, product, quantity, revenue
products          -- product ID, name, category, unit price
regions           -- region ID, name, territory manager
customers         -- customer ID, name, segment, region
```

---

## 📐 DAX Measures

```
Total Revenue = SUM(sales_orders[revenue])

YoY Growth % =
  DIVIDE(
    [Total Revenue] - CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(dates[date])),
    CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(dates[date]))
  )

Rolling 3-Month Avg =
  AVERAGEX(
    DATESINPERIOD(dates[date], LASTDATE(dates[date]), -3, MONTH),
    [Total Revenue]
  )
```

---

## 📸 Screenshots

*Screenshots coming soon — dashboard in progress.*

---

## 🔗 Live Report

*Power BI Service link coming soon.*

---

## 👩‍💻 Built By

**Sarah Halverson** — sole developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarahmhalverson)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:sarahmhalve@gmail.com)
