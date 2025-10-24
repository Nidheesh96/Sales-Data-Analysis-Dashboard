# 🧮 Sales Data Analysis & Power BI Dashboard

## 📘 Project Overview

This project analyzes historical sales data to identify key revenue drivers, seasonal trends, and actionable business insights.
It also includes a **fully interactive Power BI dashboard** that visualizes KPIs, trends, and performance across products, regions, and categories.

The project was completed in **four phases (Weeks 1–4)**:

1. **Data Cleaning & Preparation (Excel)**
2. **KPI Calculation & Visualization (Excel + Power BI)**
3. **Dashboard Design (Power BI)**
4. **Insights, Recommendations & Presentation**

---

## 📂 Project Structure

```
📦 Sales-Data-Analysis
 ┣ 📁 data
 ┃ ┣ sales_sample.xlsx            # Raw dataset
 ┃ ┗ sales_clean.xlsx             # Cleaned dataset after preprocessing
 ┣ 📁 reports
 ┃ ┣ Sales_Insights_Report.pdf    # Summary insights + recommendations
 ┃ ┗ Presentation_Slides.pptx     # Final presentation
 ┣ 📁 dashboards
 ┃ ┗ Sales_Dashboard.pbix         # Power BI dashboard file
 ┣ 📁 visuals
 ┃ ┣ PivotCharts.png              # Excel pivot chart screenshots
 ┃ ┗ Dashboard_Screenshot.png     # Power BI dashboard view
 ┣ README.md                      # Project documentation (this file)
```

---

## 🧹 Week 1 – Data Cleaning & Preparation

### Tools: Microsoft Excel

**Steps Performed:**

* Removed duplicate records
* Fixed missing or invalid dates
* Standardized category names
* Added calculated column:

  ```excel
  SalesAmount = Quantity * UnitPrice * (1 - Discount)
  ```
* Extracted `Year`, `Month`, and `MonthName` from `OrderDate`
* Created initial **PivotTables**:

  * Total Sales by Category
  * Monthly Sales Trend

**Deliverables:**

* ✅ `sales_clean.xlsx` (cleaned dataset)
* ✅ 2 PivotTables + charts
* ✅ Short note: Cleaning steps summary

---

## 📊 Week 2 – KPIs & First Visualizations

### Tools: Excel & Power BI

**KPIs Defined:**

* **Total Sales** = SUM(SalesAmount)
* **Total Orders** = COUNT of OrderID
* **Units Sold** = SUM(Quantity)
* **Average Order Value (AOV)** = Total Sales ÷ Total Orders

**Visuals Created:**

* Line chart: Monthly Sales Trend
* Bar chart: Sales by Category
* Slicers: Year, Region

**Deliverables:**

* ✅ KPI charts in Excel
* ✅ Initial Power BI file (`.pbix`)

---

## 📈 Week 3 – Power BI Dashboard Development

### Tools: Power BI Desktop

**Data Modeling:**

* Created a `Date` table:

  ```DAX
  Date = 
  ADDCOLUMNS(
    CALENDARAUTO(),
    "Year", YEAR([Date]),
    "MonthNum", MONTH([Date]),
    "MonthName", FORMAT([Date], "MMM"),
    "YearMonth", FORMAT([Date], "YYYY-MM"),
    "Quarter", "Q" & FORMAT([Date], "Q")
  )
  ```
* Linked `Sales[OrderDate]` → `Date[Date]` (One-to-Many)

**Measures Created:**

```DAX
Total Sales = SUM('Sales'[SalesAmount])
Total Orders = DISTINCTCOUNT('Sales'[OrderID])
Units Sold = SUM('Sales'[Quantity])
AOV = DIVIDE([Total Sales], [Total Orders], 0)
```

**Dashboard Layout:**

* KPI Cards (Top)
* Monthly Sales Trend (Center)
* Slicers (Left: Year, Region, Category)
* Sales by Category (Right)
* Top 10 Products (Bottom)
* Drillthrough: Product Details Page

**Deliverable:**

* ✅ Power BI dashboard (`Sales_Dashboard.pbix`)

---

## 💡 Week 4 – Insights & Recommendations

### Key Findings:

* **Top Category:** Electronics drives the majority of total sales.
* **Top Region:** North region contributes the highest revenue.
* **Seasonal Trend:** Sales peak during **Nov–Dec** (holiday season).
* **Top Products:** 10 products generate ~60% of total sales.

### Recommendations:

1. Increase inventory before the **Nov–Dec peak**.
2. Focus marketing efforts on **top-performing categories and regions**.
3. Launch **discount campaigns** during low-performing months.
4. Improve cross-selling in underperforming regions.

**Deliverables:**

* ✅ Final Dashboard
* ✅ 1-page Insight Report
* ✅ Presentation Slides

---

## 🛠️ Tools & Technologies Used

* **Microsoft Excel** (Data Cleaning, PivotTables)
* **Power BI Desktop** (Modeling, DAX, Dashboard)
* **DAX (Data Analysis Expressions)** for KPIs
* **Data Visualization** principles (interactivity, storytelling)

---


## 🧑‍💼 Author

**Name:** Nidheesh Dwivedi
**Role:** Data Analyst / BI Developer
**Tools:** Excel | Power BI | DAX | Data Storytelling
