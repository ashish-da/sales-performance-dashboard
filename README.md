# Sales Performance Dashboard — Power BI

An interactive, multi-page Power BI dashboard analyzing **10,000+ sales records** from the Kaggle Superstore dataset to uncover revenue trends, regional performance, and product-level KPIs. Built as a portfolio project to demonstrate end-to-end dashboard development using Power BI, DAX, and Power Query.

---

## Dashboard Preview

> *(Add screenshots of your 3 dashboard pages here after you finish building)*

| Page 1 — Executive Overview | Page 2 — Product Performance | Page 3 — Regional Deep Dive |
|---|---|---|
| ![Overview](screenshots/page1_overview.png) | ![Products](screenshots/page2_products.png) | ![Regional](screenshots/page3_regional.png) |

---

## Live Report

[View the interactive dashboard on Power BI Service](#) ← *(replace `#` with your published Power BI link)*

---

## Project Objective

To design and build a fully interactive executive-level sales dashboard that answers the following business questions:

1. What is the overall revenue, profit, and order volume — and how has it trended over time?
2. Which region drives the most sales and profit?
3. Which product categories and sub-categories are most and least profitable?
4. How does performance differ across customer segments (Consumer, Corporate, Home Office)?
5. Where are the biggest discount-driven profit leaks?

---

## Dataset

| Property | Details |
|---|---|
| Source | [Kaggle — Sample Superstore Sales Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) |
| Rows | 9,994 orders |
| Columns | 21 (Order ID, Date, Region, Category, Sales, Profit, Discount, etc.) |
| Time Period | 2021 – 2024 |
| Geography | United States (4 regions, 49 states) |

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development, data modelling, visualisations |
| **Power Query (M)** | Data cleaning, transformation, calculated columns |
| **DAX** | KPI measures — Total Sales, Profit Margin, MoM Growth, etc. |
| **Microsoft Excel** | Initial data exploration and validation |
| **GitHub** | Version control and project portfolio hosting |

---

## Key Features

- **KPI summary cards** — Total Sales, Total Profit, Total Orders, Profit Margin % on every page
- **Monthly revenue trend line chart** with year-over-year comparison
- **Regional sales breakdown** — bar chart + US map visual by state
- **Top 10 sub-categories** by sales and by profit margin
- **Dynamic slicers** — filter by Year, Region, Category, and Segment; synced across all 3 pages
- **Drill-through** — right-click any region to navigate to the Regional Deep Dive page
- **Custom tooltips** — hover over any bar to see Profit Margin % alongside Sales
- **Insight text boxes** on each page highlighting the single most important finding

---

## DAX Measures

```dax
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Total Orders = DISTINCTCOUNT(Orders[Order ID])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Avg Order Value = DIVIDE([Total Sales], [Total Orders], 0)

MoM Sales Growth =
VAR CurrentMonth = [Total Sales]
VAR PrevMonth = CALCULATE([Total Sales], DATEADD(DateTable[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0)
```

---

## Key Insights

> *(Update these with your actual findings once you complete the dashboard)*

- **West region** contributes ~31% of total revenue, the highest of all 4 regions
- **Technology** is the most profitable category with a ~17% profit margin
- **Tables and Bookcases** (Furniture sub-category) show negative profit margins — driven by high discounts
- **Q4 (Oct–Dec)** consistently records the highest quarterly sales across all years
- **Consumer segment** accounts for ~51% of total orders but Corporate segment has a higher average order value
- High discounts (>30%) correlate strongly with negative profit — visible in the scatter plot on Page 2

---

## Project Structure

```
sales-performance-dashboard/
│
├── Sales_Dashboard.pbix          ← Power BI project file
├── data/
│   └── superstore_sales.csv      ← Raw dataset from Kaggle
├── screenshots/
│   ├── page1_overview.png
│   ├── page2_products.png
│   └── page3_regional.png
└── README.md
```

---

## How to Open Locally

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows only)
2. Clone or download this repository
3. Open `Sales_Dashboard.pbix` in Power BI Desktop
4. If prompted about data source path, go to **Home → Transform Data → Data Source Settings** and update the path to your local `data/superstore_sales.csv`

---

## What I Learned

- Building a **multi-page Power BI report** with consistent navigation and a shared date table
- Writing **time intelligence DAX measures** (MoM growth, YoY comparison)
- Using **Power Query** to clean, reshape, and enrich raw sales data
- Designing dashboards for **non-technical stakeholders** — clear titles, insight callouts, minimal clutter
- Setting up **drill-through pages** and **synced slicers** for interactive executive reporting

---

## Author

**Ashish Rawat** — Data Analyst  
[LinkedIn](https://linkedin.com/in/ashish-da) · [GitHub](https://github.com/Ashish-da) · ashishrawat.da@gmail.com  
MCA — AI & Data Science · Graphic Era Hill University (2026)
