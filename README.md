Title: Vendor Performance Data Analytics (SQL + Python + Power BI)

Problem statement:
A company works with multiple vendors and wants to evaluate their performance based on delivery timelines, quality, and cost. The goal is to identify best and worst vendors, monitor trends, and support data‑driven decisions for negotiation and vendor management.

Objectives:

Analyze vendor performance using historical purchase order and quality data.
Calculate KPIs like on‑time delivery rate, average delay, defect rate, and return rate.
Build an interactive Power BI dashboard for business users to explore vendor performance.
(Optional) Use Python for deeper analysis or simple prediction of late deliveries.
Tech stack:

Database & queries: SQL (MySQL / PostgreSQL / SQL Server – whichever you use)
Data analysis: Python (Pandas, NumPy, Matplotlib/Seaborn)
Visualization: Power BI
You can also mention: “Inspired by Tech Classes YouTube project on Vendor Performance Analytics” with the link.

2. Data Model (Tables you’ll implement)
You can create synthetic (fake) data with this structure:

VENDORS

vendor_id (PK)
vendor_name
country
category (e.g., Raw Material, Packaging, Logistics)
start_date
PURCHASE_ORDERS

po_id (PK)
vendor_id (FK → VENDORS)
po_date
expected_delivery_date
actual_delivery_date
status (Delivered, Cancelled, Delayed, In Progress)
total_value
PO_ITEMS

po_item_id (PK)
po_id (FK → PURCHASE_ORDERS)
material_sku
description
quantity_ordered
quantity_received
unit_price
QUALITY_INSPECTIONS

inspection_id (PK)
po_id (FK → PURCHASE_ORDERS)
inspection_date
defect_flag (Yes/No)
defect_rate (0–1 or %)
return_flag (Yes/No)
return_quantity
(You can generate CSVs for each table and store them in a /data folder in your repo.)

3. Key Metrics / Logic to implement
These are the main business metrics your SQL/Python/Power BI should calculate:

Delivery delay (days)
delivery_delay_days = actual_delivery_date – expected_delivery_date

On‑time delivery rate per vendor

Orders counted as on‑time: actual_delivery_date <= expected_delivery_date
on_time_delivery_rate = on_time_orders / total_delivered_orders
Average delivery delay per vendor
Mean of delivery_delay_days for delivered orders.

Defect rate per vendor

Based on QUALITY_INSPECTIONS and/or returns.
Return rate per vendor

return_rate = total_return_quantity / total_received_quantity
Spend per vendor

Sum of total_value from PURCHASE_ORDERS.
You can also create an overall vendor score combining on‑time rate, defects, and spend (simple weighted formula in Python or Power BI).

4. Folder structure for your GitHub repo
You can organize like this:

/data

vendors.csv
purchase_orders.csv
po_items.csv
quality_inspections.csv
/sql

01_create_tables.sql
02_insert_sample_data.sql
03_vendor_kpis.sql
/notebooks or /python

vendor_performance_analysis.ipynb
/powerbi

Vendor_Performance_Dashboard.pbix
