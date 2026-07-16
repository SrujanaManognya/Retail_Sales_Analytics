#Retail_Sales Insights: End-to-End Sales & Customer Analytics

[![- Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![- Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)](#)
[![- Data Analytics](https://img.shields.io/badge/Data-Analytics-blue?style=for-the-badge)](#)

A comprehensive data analytics project that integrates multi-source retail operations data (Excel) into an interactive Power BI dashboard. This project provides enterprise-level insights into sales performance, profit optimization, customer demographics, and regional store performance.

## 📊 Business Problem & Objective
In modern retail, fragmented data across distinct entities (Sales, Customers, Products, and Stores) prevents leadership from seeing the full picture. The primary objective of this project is to centralize these data streams to answer critical business questions:
- Which product categories, sub-categories, and brands drive the highest net sales and profit margins?
- How do customer demographics (Age, Gender, Membership Type, and Segment) correlate with purchasing behaviors and payment methods?
- Which store types and geographic regions are underperforming or overperforming?
- What is the impact of product discounts on total profitability?

---

## 🗂️ Data Architecture & Schema
The project ingests data from four core dimensional and transactional files:

1. **`Sales.xlsx` (Fact Table):** Tracks transaction IDs, order dates, links to keys (`Product ID`, `Customer ID`, `Store ID`), quantities, gross sales, discounts, net sales, operational costs, total profits, and payment modes.
2. **`Customers.xlsx` (Dimension):** Details customer profile attributes including Name, Gender, Age, Location (City, State, Region), Membership Type (Silver, Gold, Platinum), and Market Segment.
3. **`Products.xlsx` (Dimension):** Catalogs internal catalog details such as Brand, Category, Sub-category, and individual Selling Price.
4. **`Stores.xlsx` (Dimension):** Tracks retail footprints including Store Name, Location, Region, and Store Type (Supermarket, Hypermarket, Mini Store).

### 🛠️ Data Modeling (Star Schema)
Data is structured using a classic **Star Schema** within Power BI to optimize DAX query performance and report responsiveness:
- **Fact Table:** `Sales`
- **Dimension Tables:** `Customers`, `Products`, and `Stores` joined via standard `1:N` relationships on surrogate/business keys.

---

## ⚡ Key Metrics & DAX Formulas Built
The dashboard relies on robust Data Analysis Expressions (DAX) to deliver dynamic KPIs:

* **Gross Sales Amount:** ```dax
    Gross Sales = SUM(Sales[Sales Amount])
    ```
* **Net Sales:** ```dax
    Net Sales = SUM(Sales[Net Sales])
    ```
* **Total Profit:** ```dax
    Total Profit = SUM(Sales[Profit])
    ```
* **Profit Margin %:** ```dax
    Profit Margin % = DIVIDE(SUM(Sales[Profit]), SUM(Sales[Net Sales]), 0)
    ```
* **Effective Discount Rate:** ```dax
    Avg Discount Rate = DIVIDE(SUM(Sales[Discount]), SUM(Sales[Sales Amount]), 0)
    ```

---

## 🎨 Dashboard Features & Views
The `Proj_1.pbix` report is broken down into structured views optimized for stakeholder decision-making:

### 1. Executive Sales Overview
- **High-Level KPIs:** Direct cards highlighting Net Sales, Total Volume, Total Profits, and Profit Margins.
- **Time-Series Analysis:** Trends showcasing sales performance over quarters and months to identify seasonality patterns.

### 2. Product & Brand Performance
- Top and bottom-performing categories (Grocery, Sports, Toys, etc.).
- Deep-dive into sub-categories to isolate high-cost items compressing margins.

### 3. Customer & Segment Demographics
- Analysis of revenue distribution by **Membership Type** (Platinum vs. Gold vs. Silver).
- Visual matrices matching payment preferences (UPI, Cards, Wallets, Cash) against consumer segments.

### 4. Regional & Store Distribution
- Geospatial and map-based visualization evaluating state-wise and city-wise metrics.
- Performance breakdown comparing **Hypermarkets** vs. **Supermarkets** vs. **Mini Stores**.

---

## 🚀 How to Setup and Run the Project

### Prerequisites
- Microsoft Excel 2016 or newer.
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Free download).
  

📈 Key Business Insights Derived
Profit Optimization: Highlights instances where high discounts fail to generate proportional sales volumes, providing actionable insights for marketing strategies.

Regional Disparities: Identifies geographical hubs generating top-tier retail traffic vs areas requiring tactical promotional campaigns.

Payment Trends: Captures the dominance of modern transaction types (like UPI/Wallets) across specific age brackets and tiers.
