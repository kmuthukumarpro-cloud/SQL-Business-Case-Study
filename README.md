# SQL Business Case Study — Sales & Customer Analytics

A business-focused SQL portfolio project that analyzes sales, customers, products, revenue, and time-based performance using a relational sales data warehouse.

The project contains 15 SQL business questions designed to demonstrate practical SQL skills used by Data Analysts.

---

## 📌 Project Overview

This project simulates a real-world sales analytics environment where business stakeholders need answers about:

- Revenue performance
- Customer spending
- Product performance
- Orders and sales volume
- Country-level performance
- Monthly revenue trends
- Customer rankings
- Product contribution
- Month-over-month growth

The objective is not only to write SQL queries, but to translate business questions into accurate and reusable analytical queries.

---

## 🎯 Business Objectives

The analysis focuses on answering the following business problems:

1. What is the total revenue?
2. How many unique customers do we have?
3. How many unique orders were placed?
4. Which product generates the highest revenue?
5. Which customer generates the highest revenue?
6. How does revenue vary by country?
7. How does revenue change month by month?
8. What is the average order value?
9. Which customers spend more than the average customer?
10. Which products generate below-average revenue?
11. How do customers rank by revenue?
12. What are the top 3 products by revenue?
13. What is the cumulative revenue over time?
14. How does monthly revenue change compared with the previous month?
15. What percentage of total revenue does each product contribute?

---

## 🗂️ Data Model

The project uses a simple sales data warehouse structure consisting of three main tables:

### `fact_sales`

Contains transaction-level sales information.

| Column | Description |
|---|---|
| `customer_key` | Unique customer identifier |
| `order_number` | Unique order identifier |
| `product_key` | Product identifier |
| `sales_amount` | Revenue generated from the transaction |
| `order_date` | Date of the transaction |

### `dim_customers`

Contains customer information.

| Column | Description |
|---|---|
| `customer_key` | Unique customer identifier |
| `country` | Customer country |

### `dim_products`

Contains product information.

| Column | Description |
|---|---|
| `product_key` | Unique product identifier |
| `product_name` | Name of the product |

> **Data grain:** `fact_sales` represents individual sales transactions. Aggregations such as revenue, customers, and orders are calculated from this transaction-level data.

---

## 🔍 Business Questions & SQL Analysis

### Basic Sales Analysis

- Total Revenue
- Total Customers
- Total Orders
- Top Product
- Top Customer

### Customer & Product Analysis

- Revenue by Country
- Customers Above Average Spend
- Customer Revenue Ranking
- Products Below Average Revenue
- Top 3 Products
- Product Revenue Contribution

### Time-Series Analysis

- Monthly Revenue
- Average Order Value
- Running Total Revenue
- Month-over-Month Revenue Growth

---

## 🧠 SQL Skills Demonstrated

This project demonstrates practical SQL techniques including:

- `SELECT`
- `WHERE`
- `GROUP BY`
- `ORDER BY`
- `HAVING`
- `DISTINCT`
- `INNER JOIN`
- `LEFT JOIN`
- Aggregate Functions
  - `SUM()`
  - `COUNT()`
  - `AVG()`
- Common Table Expressions (`CTE`)
- Subqueries
- Window Functions
- `RANK()`
- `DENSE_RANK()`
- `LAG()`
- Running Totals
- Percentage of Total
- Time-Series Analysis
- Business-oriented data analysis

---

## 📊 Key Analysis Areas

### Revenue Analysis

Revenue is analyzed at multiple levels:

- Overall revenue
- Country revenue
- Monthly revenue
- Product revenue
- Customer revenue

### Customer Analysis

Customer behavior is analyzed using:

- Total customer spending
- Average customer spending
- Customer ranking
- High-value customer identification

### Product Analysis

Product performance is evaluated using:

- Total product revenue
- Top-performing products
- Below-average products
- Revenue contribution

### Time-Series Analysis

Monthly analysis is used to understand:

- Revenue trends
- Cumulative revenue
- Month-over-month growth
- Changes in business performance over time

---

## 🧮 Example SQL Concepts

### Customer Ranking

```sql
RANK() OVER (
    ORDER BY SUM(sales_amount) DESC
)