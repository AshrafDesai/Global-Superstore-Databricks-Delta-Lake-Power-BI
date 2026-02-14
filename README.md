# Global-Superstore-Databricks-Delta-Lake-Power-BI

<img width="606" height="600" alt="image" src="https://github.com/user-attachments/assets/0ccaa351-2378-4f3d-aadb-0d2aa80bebf2" />

# 🚀 End-to-End Data Engineering & BI Project  
## Global Superstore | Databricks + Delta Lake + Power BI

---

## 📌 Project Overview

This project demonstrates a **complete end-to-end Modern Data Engineering pipeline** using:

- 🧱 **Medallion Architecture (Bronze → Silver → Gold)**
- ⚡ **Databricks & Delta Lake**
- 🗂 **Unity Catalog**
- 📊 **Star Schema Dimensional Modeling**
- 📈 **Power BI Dashboarding**

The goal was to transform raw retail transactional data into a **production-ready analytical model** and deliver executive-level business insights.

---

## 🏗 Architecture

```
Raw CSV File
↓
Bronze Layer (Raw Ingestion)
↓
Silver Layer (Cleaned & Transformed)
↓
Gold Layer (Star Schema)
↓
Power BI Dashboard

```

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| Storage | Delta Lake |
| Data Engineering | Databricks |
| Governance | Unity Catalog |
| Query Engine | Databricks SQL |
| Data Modeling | Star Schema |
| Visualization | Power BI |
| Language | SQL |

---

## 📂 Dataset

**Dataset:** Global Superstore  
**Format:** CSV  
**Content:** Retail transactional sales data  

### Key Fields:
- Order ID
- Order Date
- Ship Date
- Customer Information
- Product Information
- Sales
- Quantity
- Discount
- Profit
- Shipping Cost

---

# 🥉 Bronze Layer – Raw Ingestion

### Objective:
Store raw data exactly as received.

### Process:
- Created Unity Catalog
- Created Schema
- Created Volume
- Uploaded CSV
- Loaded raw CSV into Delta table

### Characteristics:
- No transformations
- Schema minimally enforced
- Serves as raw data source

---

# 🥈 Silver Layer – Data Cleaning & Transformation

### Objective:
Clean and standardize the data.

### Transformations:
- Converted date columns to proper `DATE` type
- Cast numeric fields (sales, profit, discount)
- Removed malformed values using `try_cast`
- Filtered null order IDs
- Standardized column names

### Outcome:
Clean, query-ready dataset for dimensional modeling.

---

# 🥇 Gold Layer – Dimensional Modeling (Star Schema)

## ⭐ Star Schema Design

### Fact Table
`fact_sales`
- order_id
- customer_key
- product_key
- location_key
- date_key
- sales
- quantity
- discount
- profit
- shipping_cost

---

### Dimension Tables

#### 🧑 dim_customer
- customer_key (surrogate)
- customer_id
- customer_name
- segment

#### 📦 dim_product
- product_key
- product_id
- product_name
- category
- sub_category

#### 🌍 dim_location
- location_key
- country
- city
- state
- region
- postal_code

#### 📅 dim_date
- date_key
- year
- month
- day
- month_name
- week_number
- quarter

---

# 🔍 Data Modeling Strategy

- Implemented surrogate keys
- Many-to-One relationships
- Fact table joins dimension tables
- Optimized for BI tools
- Follows Kimball methodology

---

# ⚡ Optimization

- Stored tables in Delta format
- Used `OPTIMIZE`
- Applied `ZORDER BY`
- Validated referential integrity
- Verified null foreign keys

---

# 📊 Power BI Dashboard

## Page 1 — Executive Overview

- Total Sales
- Total Profit
- Profit Margin %
- Total Orders
- Sales by Category
- Profit by Region
- Monthly Sales Trend

---

## Page 2 — Product Performance

- Sales by Sub Category
- Top 10 Products by Profit
- Discount vs Profit (Scatter Plot)

### Insights:
- Identified high-revenue categories
- Detected margin erosion due to discounting
- Highlighted high-margin products

---

## Page 3 — Customer Insights

- Sales by Segment
- Top Customers
- Orders by Region

### Insights:
- Customer segmentation performance
- VIP customer identification
- Regional demand patterns

---

# 📐 DAX Measures Used

```
DAX
Total Sales = SUM(fact_sales[sales])

Total Profit = SUM(fact_sales[profit])

Profit Margin % = DIVIDE([Total Profit], [Total Sales])

Total Orders = DISTINCTCOUNT(fact_sales[order_id])

Avg Discount = AVERAGE(fact_sales[discount])
```

# Skills Demonstrated

* Modern Data Engineering

* Databricks SQL

* Delta Lake Optimization

* Unity Catalog Governance

* Dimensional Modeling

* Star Schema Design

* Power BI Development

* DAX

* Data Quality Handling

**Author:** 
Asharafraza Desai  
Data Engineer | Analytics Engineer | BI Developer  
