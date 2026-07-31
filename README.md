# 🚚 Logistics & Supply Chain Analytics Dashboard

An end-to-end **Power BI** dashboard built on the DataCo Supply Chain dataset to monitor logistics operations, track delivery performance, and drive supply chain efficiency across every market — from raw data to a fully interactive, decision-ready report.

![Status](https://img.shields.io/badge/status-completed-brightgreen)
![Tool](https://img.shields.io/badge/Power%20BI-Desktop-yellow)
![Language](https://img.shields.io/badge/DAX-100%2B%20measures-blueviolet)

---

## 📌 Overview

This project is a 4-page executive-level Power BI dashboard that transforms raw order/shipment-level data into actionable logistics and sales intelligence. It covers the full analytics lifecycle: data modeling, relationship debugging, DAX measure engineering, and interactive report design.

**Live headline metrics:**

| KPI | Value |
|---|---|
| Total Shipments | 181K |
| Total Sales | $37M |
| On Time Deliveries | 32.2K |
| Late Deliveries | 99K |
| Total Customers | 21K |
| Total Profit | $3.97M |
| Profit Margin | 10.78% |
| Avg Order Value | $559.45 |

---

## 🖥️ Dashboard Pages

### 🏠 Home Page
Landing page with report navigation and project branding.

![Home Page](./Screenshots/HomePage%20(1).png)

### 1. Executive Summary
High-level KPI overview with YoY comparison cards (Total Shipments, Total Sales, Late/On-Time Deliveries), a shipments trend line chart, delivery status breakdown donut, and a regional shipments map.

![Executive Summary](./Screenshots/Executive%20Summary.png)

### 2. Delivery Performance
Deep-dive into service quality — On Time Delivery %, Late Delivery %, Avg Shipping Delay, Cancellation Rate — broken down by Shipping Mode and Order Region, with a dynamic "most delayed shipping mode" insight card.

![Delivery Performance](./Screenshots/Delivery%20Performance.png)

### 3. Sales & Profitability
Revenue, profit, margin, and average order value trends with previous-year benchmarking on every card.

![Sales & Profitability](./Screenshots/Sales%20&%20Profitability.png)

### 4. Geographic Analysis
Market and region-level breakdown of shipments, sales, and delivery performance for spatial pattern discovery.

![Geographic Analysis](./Screenshots/Geograhpic%20Analysis.png)

---

## 🧠 Key Technical Work

This wasn't just a drag-and-drop dashboard — several real modeling problems were diagnosed and solved:

- **Critical relationship bug fix:** Discovered that `Fact Orders[Order Date]` (a DateTime column with time-of-day values) was joined to `Dim Date[Date]` (pure dates) as an *exact match* relationship — silently orphaning **99.93% of fact rows** from the calendar table and inflating YoY growth figures to absurd levels (145,000%+). Fixed by engineering clean, time-truncated date key columns and rebuilding the relationship correctly.
- **100+ DAX measures** covering core KPIs, YoY/PY comparisons, dynamic conditional formatting (background/font color measures), and a reusable **dynamic KPI-switching pattern** (disconnected selector table + `SELECTEDVALUE` + `SWITCH`) to power a single scalable scorecard visual instead of duplicating cards.
- **Consistent, presentation-ready number formatting** (K/M suffixes, percentage-point vs. relative-percent handling) applied uniformly across every KPI card.
- **Dynamic storytelling measures**, e.g. a "Most Delayed Shipping Mode" card that automatically surfaces the worst-performing shipping mode and its delay gap — rather than hiding it inside a flat average.

---

## 🛠️ Tools & Tech Stack

- **Power BI Desktop** — data modeling, report design
- **DAX** — measures, YoY logic, dynamic KPI switching, conditional formatting
- **Power Query (M)** — data cleaning and transformation
- **Star Schema** data modeling
- **DataCo Global Supply Chain** dataset

---

## 📂 Repository Structure

```
├── Logistics Supply Chain Dashboard.pbix   # Main Power BI report
├── Screenshots/                             # Dashboard page screenshots
│   ├── HomePage (1).png
│   ├── Executive Summary.png
│   ├── Delivery Performance.png
│   ├── Sales & Profitability.png
│   └── Geograhpic Analysis.png
└── README.md
```

---

## 🚀 How to Use

1. Clone this repository
2. Open `Logistics Supply Chain Dashboard.pbix` in **Power BI Desktop**
3. Explore the report pages using the navigation panel and slicers (Market, Shipping Mode, Order Date, Year-Month, Delivery Status)

---

## 👤 Author

**Touqeer**
Business Intelligence Developer | Data Analyst
📍 Rawalpindi, Pakistan

Connect with me on [LinkedIn](#) for more Power BI & data analytics projects.

---

⭐ If you find this project useful, consider giving it a star!
