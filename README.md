# 📊 Vendor Performance Data Analytics

### SQL + Python + Power BI Project

## 🚀 Project Overview

This project focuses on analyzing vendor performance using historical procurement and quality inspection data. The goal is to help organizations evaluate vendors based on delivery timelines, product quality, return rates, and overall procurement spending.

By leveraging **SQL, Python, and Power BI**, this project provides actionable insights that support better vendor management, strategic sourcing, and data-driven negotiation decisions.

---

## 🎯 Problem Statement

Organizations working with multiple vendors often face challenges in tracking delivery efficiency, product quality, and procurement costs. Poor vendor performance can lead to delayed operations, increased returns, and higher business risks.

This project aims to identify:

* ✅ Best-performing vendors
* ⚠️ Vendors with frequent delays or defects
* 📈 Performance trends over time
* 💰 Vendor spending insights

---

## 🧩 Objectives

* Analyze vendor performance using purchase order and quality inspection data.
* Calculate key procurement KPIs and operational metrics.
* Build an interactive Power BI dashboard for business users.
* Perform exploratory data analysis using Python.
* Support data-driven vendor evaluation and decision-making.
* *(Optional)* Predict late deliveries using Python-based analysis.

---

## 🛠️ Tech Stack

| Technology                                      | Purpose                            |
| ----------------------------------------------- | ---------------------------------- |
| **SQL** (MySQL / PostgreSQL / SQL Server)       | Data storage & KPI queries         |
| **Python** (Pandas, NumPy, Matplotlib, Seaborn) | Data analysis & visualization      |
| **Power BI**                                    | Interactive dashboards & reporting |

---

# 🗂️ Data Model

## 1️⃣ VENDORS

Contains vendor master information.

| Column Name    | Description            |
| -------------- | ---------------------- |
| vendor_id (PK) | Unique vendor ID       |
| vendor_name    | Vendor name            |
| country        | Vendor location        |
| category       | Vendor category        |
| start_date     | Vendor onboarding date |

---

## 2️⃣ PURCHASE_ORDERS

Stores purchase order transaction details.

| Column Name            | Description           |
| ---------------------- | --------------------- |
| po_id (PK)             | Purchase order ID     |
| vendor_id (FK)         | Linked vendor ID      |
| po_date                | Order date            |
| expected_delivery_date | Planned delivery date |
| actual_delivery_date   | Actual delivery date  |
| status                 | Order status          |
| total_value            | Total PO value        |

---

## 3️⃣ PO_ITEMS

Contains item-level purchase details.

| Column Name       | Description           |
| ----------------- | --------------------- |
| po_item_id (PK)   | PO item ID            |
| po_id (FK)        | Linked purchase order |
| material_sku      | Material SKU          |
| description       | Item description      |
| quantity_ordered  | Ordered quantity      |
| quantity_received | Received quantity     |
| unit_price        | Price per unit        |

---

## 4️⃣ QUALITY_INSPECTIONS

Stores quality inspection and return information.

| Column Name        | Description               |
| ------------------ | ------------------------- |
| inspection_id (PK) | Inspection ID             |
| po_id (FK)         | Linked purchase order     |
| inspection_date    | Inspection date           |
| defect_flag        | Indicates defect presence |
| defect_rate        | Percentage of defects     |
| return_flag        | Indicates returns         |
| return_quantity    | Returned quantity         |

---

# 📌 Key Business Metrics

## 📅 Delivery Delay

Measures the number of delayed days.

```sql
delivery_delay_days = actual_delivery_date - expected_delivery_date
```

---

## 🚚 On-Time Delivery Rate

Percentage of orders delivered on or before the expected date.

```sql
on_time_delivery_rate = on_time_orders / total_delivered_orders
```

Condition:

```sql
actual_delivery_date <= expected_delivery_date
```

---

## ⏳ Average Delivery Delay

Average delayed days per vendor.

---

## 🏭 Defect Rate

Measures product quality issues using inspection records.

---

## 🔄 Return Rate

Tracks returned quantity against received quantity.

```sql
return_rate = total_return_quantity / total_received_quantity
```

---

## 💰 Spend Per Vendor

Total procurement spend for each vendor.

```sql
SUM(total_value)
```

---

## ⭐ Vendor Performance Score

A weighted performance score based on:

* On-time delivery rate
* Defect rate
* Return rate
* Vendor spend

---

# 📊 Dashboard Features (Power BI)

The interactive dashboard includes:

* 📈 Vendor performance trends
* 🚚 Delivery performance analysis
* 🏭 Quality & defect insights
* 🔄 Return analysis
* 💰 Procurement spending overview
* 🏆 Top & bottom vendor ranking
* 📅 Time-based filtering & drilldowns

---

# 🧪 Python Analysis

Python is used for:

* Data cleaning & preprocessing
* Exploratory Data Analysis (EDA)
* KPI calculations
* Trend analysis
* Visualization using Matplotlib & Seaborn
* *(Optional)* Predicting late deliveries

---

# 📁 Project Structure

```bash
Vendor-Performance-Analytics/
│
├── data/
│   ├── vendors.csv
│   ├── purchase_orders.csv
│   ├── po_items.csv
│   └── quality_inspections.csv
│
├── sql/
│   ├── 01_create_tables.sql
│   ├── 02_insert_sample_data.sql
│   └── 03_vendor_kpis.sql
│
├── python/
│   └── vendor_performance_analysis.ipynb
│
├── powerbi/
│   └── Vendor_Performance_Dashboard.pbix
│
└── README.md
```

---

# 📚 Learning Source

Inspired by the **Tech Classes YouTube Project on Vendor Performance Analytics**.

You can add the project/tutorial link here:

```text
https://youtube.com/
```

---

# 📌 Future Enhancements

* Machine Learning model for vendor risk prediction
* Automated reporting pipeline
* Real-time dashboard integration
* Supplier segmentation analysis
* Advanced procurement analytics

---

# 🙌 Conclusion

This project demonstrates how data analytics can improve procurement efficiency and vendor management through KPI-driven insights and interactive business intelligence dashboards.

It showcases practical skills in:

* SQL querying
* Data analysis
* Dashboard development
* Business intelligence
* Procurement analytics

---

# 👨‍💻 Developed By

### Naveen KR

A data analytics project built using SQL, Python, and Power BI to analyze vendor performance and support data-driven business decisions.
