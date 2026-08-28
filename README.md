# Data_Modelling
# Omnichannel Retail Analytics Dashboard

## 📌 Project Overview
This project builds a complete end-to-end business intelligence pipeline inside Power BI Desktop. It transforms a disconnected, raw multi-table retail dataset into an optimized, interactive star-schema analytical model to uncover sales trends, product rankings, and customer demographics.

## 📊 Relational Data Model (Star Schema)
The architecture breaks away from a flat-file setup, organizing data into an optimized **Star Schema** for faster processing:
* **Fact Table:** `Sales_Transactions` (stores transactional revenue, quantity, and relational keys).
* **Dimension Tables:** `Customer_Master` and `Product_Catalog` (store descriptive details).

### Relationships Configuration
* `Customer_Master [Customer_ID]` 1 ─── * `Sales_Transactions [Customer_ID]` (Single Direction)
* `Product_Catalog [Product_ID]` 1 ─── * `Sales_Transactions [Product_ID]` (Single Direction)

## 💡 Analytical Expressions (DAX Measures)
The following explicit DAX measures were written to drive the visual canvas:
```DAX
Total Sales = SUM('Sales_Transactions'[Revenue])

Total Orders = DISTINCTCOUNT('Sales_Transactions'[OrderID])

Average Order Value = DIVIDE([Total Sales], [Total Orders], 0)
```

## 🎨 Visual Dashboard Layout
The final dashboard features a 3-tier visual layout designed for quick scanning:
1. **KPI Cards:** Show high-level metrics like **Total Sales** and **Total Orders** at a glance.
2. **Bar Chart:** Ranks top-performing **Product Categories** by sales volume.
3. **Line Chart:** Tracks **Temporal Sales Trends** over a multi-year monthly timeline.
4. **Pie Chart:** Breaks down buyer market share across different **Customer Segments**.
5. **Slicer Control:** Filters the entire report by **Region** with a single click.

## 🚀 How to Run this Project Locally
1. Clone this repository to your computer.
2. Download and install [Power BI Desktop](https://microsoft.com).
3. Open the `Retail_Sales_Model.pbix` file to explore the interactive model.
