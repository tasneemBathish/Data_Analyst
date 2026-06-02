# E-Commerce Sales Analysis

Dataset:
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

1) Olist E-Commerce Ecosystem Analysis (SQL):
Project Overview:
This folder contains the core Data Engineering and Exploratory Data Analysis (EDA) phase of the Olist E-commerce project. The goal was to transform raw, fragmented CSV files into a structured, high-performance Relational Database to extract actionable business insights.

Data Pipeline & Technical Challenges:
1. Schema Design (DDL)
I designed a relational schema consisting of 9 interconnected tables, ensuring proper data types for performance optimization (e.g., using DECIMAL for financial figures and DATETIME for timestamps).

2. Advanced Data Ingestion
Loading the Olist dataset into MySQL presented several real-world challenges which were resolved using advanced SQL techniques:
Handling Inconsistent Delimiters: Implemented OPTIONALLY ENCLOSED BY '"' and ESCAPED BY '"' to handle complex text fields in reviews.
Solving Server Restrictions: Resolved Error 1290 (--secure-file-priv) by utilizing designated server paths.
Flexible Data Loading: Used VARCHAR temporarily for inconsistent date fields to ensure 100% data ingestion before the cleaning phase.

3. Data Transformation (The Fact Table)
To streamline the analysis, I built a consolidated Fact Table called cleaned_orders.
Joins & Relationships: Performed complex JOIN operations across 5 tables (Orders, Customers, Items, Products, and Translations).
Dynamic Data Cleaning: Used STR_TO_DATE() to standardize timestamps.
Business Logic Layer: Filtered for delivered orders only to ensure financial reports reflect actual realized revenue.

Key Exploratory Queries:
The E-Commerce-Sales-Analysis.sql file includes specialized queries to answer critical business questions:
1. Sales Momentum: Analyzing monthly revenue trends to identify seasonal peaks.
2. Product Performance: Ranking categories by total revenue and units sold.
3. Logistics Efficiency: Measuring the gap between Actual vs Estimated delivery times using DATEDIFF().

Sample SQL Insights:
Total Master Records: 108,638 transaction lines.
Top Growth Period: November 2017 showed a massive revenue spike.
Average Delivery Speed: 12 days (significantly outperforming the 24 days estimated).
