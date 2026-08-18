# 📊 Business Sales Performance Analytics

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Visualization-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Analytics](https://img.shields.io/badge/Data%20Analytics-Business%20Insights-2563EB?style=for-the-badge)
![Future Interns](https://img.shields.io/badge/Future%20Interns-Task%201-16A34A?style=for-the-badge)

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
- Removed/handled data type errors where required

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
