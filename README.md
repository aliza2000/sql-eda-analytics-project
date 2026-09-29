# sql-eda-analytics-project
# SQL EDA & Advanced Analytics Project

This repository contains SQL scripts I wrote while completing a full data 
exploration and analytics project on a sales dataset (customers, products, 
and sales transactions). It covers everything from basic database 
exploration to advanced analytics — including cumulative trends, 
year-over-year performance, part-to-whole analysis, and customer/product 
segmentation with reusable reporting views.

I built this project to practice turning raw relational data into real 
business insights using SQL — the kind of analysis a data analyst would 
actually be asked to do on the job. Each query is commented to explain 
what it does and why.

## Tools Used
- PostgreSQL / pgAdmin
- SQL (joins, aggregation, CTEs, window functions, views, date functions)

## What I Explored

**1. Database Exploration**
- Listed all tables and columns using `INFORMATION_SCHEMA`
- Explored distinct customer countries and product categories

**2. Date Range & Customer Exploration**
- First and last order date, and the total time span between them
- Oldest and youngest customer by birthdate

**3. Key Business Measures**
- Total sales, total items sold, average selling price
- Total orders, total products, total customers, and customers who placed at least one order
- Combined all of the above into a single summary report using `UNION ALL`

**4. Magnitude Analysis**
- Customers by country and by gender
- Products by category, and average cost per category
- Total revenue by category and by individual customer
- Distribution of items sold across countries

**5. Ranking Analysis**
- Top 5 and bottom 5 products by revenue

**6. Time-Based & Cumulative Analysis**
- Yearly sales performance and customer counts
- Monthly running total of sales using window functions

**7. Performance Analysis (Year-over-Year)**
- Compared each product's yearly sales to its own average performance
- Compared each product's yearly sales to the previous year's sales, flagging increase/decrease using `LAG()`

**8. Part-to-Whole Analysis**
- Each product category's percentage share of total revenue

**9. Segmentation**
- Products segmented into cost ranges (Below 100, 100-500, 500-1000, Above 1000)
- Customers segmented into VIP / Regular / New based on spending and lifespan

**10. Reusable Reporting Views**
- `gold.report_customers` — consolidated customer-level view with age groups, segments, recency, average order value, and average monthly spend
- `gold.report_products` — consolidated product-level view with performance segments (High/Mid/Low performer), recency, average order revenue, and average monthly revenue

## Key Insights
- Bikes is the dominant category, generating 96.46% of total sales ($113.27M of $117.43M total revenue) — Accessories and Clothing together make up less than 4%
- Most products fall into the "Below 100" cost range (220 products), suggesting the catalog is weighted toward lower-cost items
- Customer segmentation shows the majority are New (14,631), a small VIP group (3,827), and very few Regular customers (26) — an unusually thin middle tier worth investigating further

## Note
This project follows the SQL Exploratory Data Analysis and Advanced 
Analytics framework taught by Data With Baraa, using his public gold-layer 
dataset. I wrote, ran, and debugged all queries myself in PostgreSQL 
(pgAdmin), converting the original SQL Server syntax (DATEDIFF, YEAR, 
GETDATE, BULK INSERT, etc.) to PostgreSQL equivalents throughout the project.
