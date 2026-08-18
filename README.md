# 📊 Business Sales Performance Analytics

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Visualization-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analytics](https://img.shields.io/badge/Data%20Analytics-Business%20Insights-2563EB?style=for-the-badge)
![Future Interns](https://img.shields.io/badge/Future%20Interns-Task%201-16A34A?style=for-the-badge)

---

## 📌 Project Overview

This project was completed as part of the **Data Science & Analytics Internship – Task 1** by **Future Interns**.

The objective of this project is to analyze business sales data and develop an interactive, client-ready **Power BI dashboard** that helps businesses understand their sales performance, profitability, customer segments, product performance, and regional trends.

The analysis focuses on transforming raw sales data into meaningful business insights and actionable recommendations.

---

## 🎯 Business Objective

The primary goal of this project is to answer important business questions such as:

- Which products generate the highest sales?
- Which products and categories generate the highest profit?
- How do sales change over time?
- Which regions perform the best?
- Which customer segments contribute the most revenue?
- Which sub-categories are most profitable?
- Does discounting have an impact on profitability?
- Where should the business focus its growth efforts?

---

## 🗂️ Dataset

The project uses the **Sample Superstore** sales dataset provided for the internship task.

The dataset contains transactional sales information including:

- Order details
- Customer information
- Product information
- Geographic information
- Sales
- Quantity
- Discount
- Profit
- Shipping information

The dataset contains approximately **10,000 transaction records**.

---

## 🧹 Data Cleaning & Preparation

The raw CSV dataset was imported into **Power BI Power Query** and prepared for analysis.

### Data preparation steps included:

- Imported the complete dataset rather than analyzing only a sample of rows
- Promoted the first row as column headers
- Verified column names and structure
- Corrected data types
- Converted Order Date to Date
- Converted Ship Date to Date
- Converted Sales to Decimal Number
- Converted Profit to Decimal Number
- Converted Discount to Decimal Number
- Converted Quantity to Whole Number
- Kept Order ID, Customer ID, Product ID, and other categorical identifiers as Text
- Checked column quality and data validity
- Handled data type errors where required

---

## 📅 Date Table

A dedicated Date Table was created using DAX to support time-based analysis and interactive filtering.

```DAX
Date Table =
ADDCOLUMNS(
    CALENDAR(
        MIN('Sample - Superstore'[Order Date]),
        MAX('Sample - Superstore'[Order Date])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Year Month", FORMAT([Date], "YYYY-MM"),
    "Quarter", "Q" & FORMAT([Date], "Q")
)
The Date Table was connected to the main sales table using:

Date Table[Date] → Sample - Superstore[Order Date]

A one-to-many relationship was used.

📈 Key Performance Indicators

The dashboard contains several business-focused KPIs.

💰 Total Sales
Total Sales =
SUM('Sample - Superstore'[Sales])
💚 Total Profit
Total Profit =
SUM('Sample - Superstore'[Profit])
📦 Total Orders
Total Orders =
DISTINCTCOUNT('Sample - Superstore'[Order ID])
👥 Total Customers
Total Customers =
DISTINCTCOUNT('Sample - Superstore'[Customer ID])
📊 Total Quantity
Total Quantity =
SUM('Sample - Superstore'[Quantity])
📈 Profit Margin
Profit Margin =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
📊 Previous Year Sales
Previous Year Sales =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR('Date Table'[Date])
)
📈 Sales Growth %
Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
📊 Dashboard Structure

The Power BI report is organized into two main analytical pages.

1️⃣ Executive Sales Dashboard

The first page provides a high-level overview of business performance.

KPI Cards
Total Sales
Total Profit
Profit Margin
Total Orders
Total Customers
Total Quantity
Interactive Filters
Year
Region
Category
Customer Segment
Ship Mode
Visualizations
Monthly Sales Trend
Sales & Profit by Category
Regional Sales Performance
Sales Contribution by Sub-Category

The slicers are synchronized across dashboard pages to provide consistent filtering.

2️⃣ Product & Customer Analysis

The second page provides deeper analysis of product and customer performance.

Analysis includes:
Top 10 Products by Sales
Top 10 Products by Profit
Sales Contribution by Sub-Category
Profit by Sub-Category
Customer Segment Performance
Discount vs Profitability
Geographic Sales Performance

This page is designed to help identify products, customers, regions, and business areas that require attention or present growth opportunities.

🎨 Dashboard Design

The dashboard uses a bright, professional color palette designed for business reporting.

Business Metric	Color
Sales	🔵 Bright Blue
Profit	🟢 Green
Orders	🩵 Teal
Customers	🟣 Purple
Quantity	🟠 Orange
Negative Performance	🔴 Red
Background	🩵 Light Blue
Cards	⚪ White

The dashboard uses a consistent visual language so that colors have a clear business meaning throughout the report.

🔍 Key Analytical Areas
📈 Sales Trend Analysis

Monthly sales trends are analyzed to identify:

Growth patterns
Seasonal fluctuations
High-performing periods
Low-performing periods
Changes in sales performance over time
🏆 Product Performance

Product-level analysis identifies:

Top-selling products
Most profitable products
Products with high revenue but weaker profitability
Product opportunities for business growth
📦 Category & Sub-Category Analysis

Category and sub-category analysis helps determine:

Which categories generate the most revenue
Which categories generate the most profit
Which sub-categories contribute significantly to sales
Potential areas of weak profitability
🌎 Regional Analysis

Regional analysis helps identify:

High-performing regions
Low-performing regions
Geographic sales concentration
Potential opportunities for regional expansion
👥 Customer Segment Analysis

Customer segments are compared based on:

Sales contribution
Profit contribution
Order activity
Overall business value

The analysis focuses on:

Consumer
Corporate
Home Office
💸 Discount & Profitability Analysis

A scatter plot is used to analyze the relationship between:

Discount → Profit

with sales volume represented through bubble size and product categories used for comparison.

This helps investigate whether higher discounts are associated with lower profitability.

💡 Business Insights

The dashboard is designed to help stakeholders identify insights such as:

1. Revenue Concentration

A small number of products and sub-categories may contribute a significant portion of total revenue.

Recommendation:
Prioritize high-performing products through inventory planning, marketing, and promotional strategies.

2. Revenue vs Profit

Products with high sales are not necessarily the most profitable.

Recommendation:
Evaluate products using both revenue and profit rather than sales alone.

3. Regional Opportunities

Regional analysis can reveal areas with strong sales as well as regions with growth potential.

Recommendation:
Focus marketing and sales resources on high-potential regions while investigating underperforming regions.

4. Discount Management

Excessive discounting can potentially reduce profit margins.

Recommendation:
Evaluate discount strategies based on profitability rather than using discounts purely to increase sales volume.

5. Customer Segmentation

Different customer segments contribute differently to revenue and profit.

Recommendation:
Develop targeted strategies for high-value customer segments and identify opportunities to increase customer retention and order value.

📌 Business Recommendations

Based on the dashboard analysis, businesses can consider the following actions:

🚀 1. Focus on High-Performing Products

Prioritize products that consistently generate strong sales and profit.

💰 2. Optimize Discount Strategies

Avoid excessive discounting on products with already-low margins.

🌎 3. Strengthen Regional Strategy

Allocate marketing and sales resources based on regional performance and growth opportunities.

👥 4. Develop Segment-Specific Strategies

Create targeted offers and campaigns for different customer segments.

📦 5. Improve Product Portfolio Decisions

Use both sales and profitability metrics when deciding which products to promote, expand, or review.

📈 6. Monitor Trends Regularly

Use the dashboard as an ongoing reporting tool to track changes in sales and profitability.

🛠️ Tools & Technologies
Power BI
Power Query
DAX
Microsoft Excel / CSV
Data Visualization
Business Intelligence
Data Cleaning
Exploratory Data Analysis
📁 Project Structure
Business-Sales-Performance-Analytics/
│
├── README.md
│
├── Dataset/
│   └── Sample - Superstore.csv
│
├── PowerBI/
│   └── Business Sales Performance Analytics.pbix
│
├── Dashboard/
│   ├── Executive Sales Dashboard.png
│   └── Product & Customer Analysis.png
│
└── Documentation/
    └── Business Insights & Recommendations.pdf

File names can be adjusted according to the files included in the final repository.

📊 Project Workflow
Raw Sales Data
      ↓
Data Cleaning
      ↓
Data Type Correction
      ↓
Power Query Transformation
      ↓
Date Table Creation
      ↓
Data Modeling
      ↓
DAX Measures
      ↓
KPI Development
      ↓
Interactive Dashboard
      ↓
Business Analysis
      ↓
Insights & Recommendations
🎓 Internship Information

Program: Data Science & Analytics Internship

Organization: Future Interns

Task: Task 1 – Business Sales Performance Analytics

Project Type: Business Intelligence / Data Analytics

🚀 Skills Demonstrated

Through this project, I demonstrated practical skills in:

Data Cleaning
Data Preparation
Power Query
Data Modeling
DAX
KPI Development
Time-Series Analysis
Sales Analysis
Profitability Analysis
Customer Segmentation
Product Analysis
Regional Analysis
Interactive Dashboard Development
Business Intelligence
Data Visualization
Business Storytelling
Insight Generation
Actionable Recommendations
👨‍💻 Author
Chinmay Suryawanshi

Computer Science Engineering – AI & Data Science

Areas of Interest
Data Analytics
Data Science
Business Intelligence
Power BI
Data Visualization
Machine Learning
Artificial Intelligence
⭐ Project Outcome

This project transformed raw transactional sales data into an interactive business intelligence dashboard capable of helping stakeholders monitor sales performance, analyze profitability, identify high-performing products and regions, and make data-driven business decisions.

The project demonstrates how data analytics can move beyond visualization to support practical business decision-making.

📌 Future Improvements

Potential future enhancements include:

Adding sales forecasting
Adding year-over-year performance dashboards
Creating customer lifetime value analysis
Adding advanced profitability metrics
Implementing automated data refresh
Adding drill-through product detail pages
Creating dynamic KPI commentary
Developing predictive sales models
Publishing the dashboard through Power BI Service

⭐ If you found this project useful, consider giving the repository a star!
