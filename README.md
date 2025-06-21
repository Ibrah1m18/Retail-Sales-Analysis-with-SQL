# Retail Sales Analysis with SQL

A beginner-friendly SQL project analyzing a fictional retail dataset to answer business questions about sales, customer demographics, and trends.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Setup Instructions](#setup-instructions)
- [SQL Queries and Analysis](#sql-queries-and-analysis)
- [Key Findings](#key-findings)
- [Future Improvements](#future-improvements)
- [Author](#author)

## Project Overview

This project analyzes a ready-made retail sales dataset using MySQL. The main objective is to explore sales performance and customer behavior by examining categories, total sales, order dates, age groups, and gender. Through a series of SQL queries, the project answers key business questions and practices essential SQL techniques such as filtering, grouping, and aggregating data.

## Setup Instructions

1. Clone or download this repository.
2. Make sure you have MySQL installed (e.g. MySQL Workbench).
3. Create a new database (e.g. `retail_db`) in MySQL.
4. Use the following command or import tool to load the CSV file into a new table:

```sql
LOAD DATA INFILE '/path/to/retail_sales.csv'
INTO TABLE retail_sales
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
```

5. Open the SQL file (`retail_sales_queries.sql`) and run the queries step-by-step to explore and analyze the data.

## SQL Queries and Analysis

Below are the key types of SQL queries used in this project:

- **Total Sales by Category**  
  Aggregated sales amount per product category using `GROUP BY`.
```sql
-- Total Sales by Category
SELECT category, SUM(sales) AS total_sales
FROM retail_sales
GROUP BY category;
```
- **Sales Over Time**  
  Analyzed total sales by date to observe trends and peak periods.
```sql
-- Sales Over Time
SELECT sales_date, SUM(sales) AS total_sales
FROM retail_sales
GROUP BY sales_date
ORDER BY sales_date;
```
- **Customer Demographics**  
  Explored the distribution of customers by age and gender.
```sql
-- Customer Demographics
SELECT age, gender, COUNT(*) AS number_of_customers
FROM retail_sales
GROUP BY age, gender;
```
- **Order Volume by Gender**  
  Counted number of orders made by male and female customers.
```sql
-- Order Volume by Gender
SELECT gender, COUNT(*) AS order_count
FROM retail_sales
GROUP BY gender;
```
- **High-Value Orders**  
  Filtered for orders with total sales above a certain threshold.
```sql
-- High-Value Orders
SELECT * 
FROM retail_sales
WHERE sales > 1000;
```
Each query was executed using basic SQL clauses such as `SELECT`, `WHERE`, `GROUP BY`, `ORDER BY`, and simple conditional filters.

## Key Findings

- The top-selling category is **Clothing**, accounting for approximately 35% of total sales.
- Most high-value orders (above $1000) occur during evening hours.
- Female customers placed more orders than male customers in the **Beauty** category.

## Future Improvements

- Create visual dashboards using Power BI or Tableau based on the same dataset.
- Add more dimensions like payment method or location for deeper insights.
- Apply more advanced SQL queries such as subqueries or CTEs.

## Author

**Ibrahim Ahmed**  
Aspiring Data Analyst | SQL | Power BI | Python  
📫 [Connect on LinkedIn](https://www.linkedin.com/in/ibrahim-ahmed-572475143/)
