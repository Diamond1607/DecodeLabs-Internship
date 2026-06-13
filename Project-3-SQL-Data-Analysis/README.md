# Project 3: SQL Data Analysis

## Objective
Use SQL queries to analyze a sales dataset and extract meaningful business insights.

## Tasks Performed
- Retrieved data using SELECT statements
- Filtered records using WHERE clauses
- Sorted results using ORDER BY
- Grouped data using GROUP BY
- Performed aggregations using COUNT(), SUM(), and AVG()

## Tools Used
- MySQL Workbench
- SQL

## SQL Queries Used

### Total Number of Orders
```sql
SELECT COUNT(*) AS Total_Orders
FROM sales_data;

### Average Unit Price
```sql
SELECT AVG(UnitPrice) AS Average_Unit_Price
FROM sales_data;

### Revenue by Product
```sql
SELECT Product,
       SUM(TotalPrice) AS Revenue
FROM sales_data
GROUP BY Product
ORDER BY Revenue DESC;

### Orders by Payment Method
```sql
SELECT PaymentMethod,
       COUNT(*) AS Total_Orders
FROM sales_data
GROUP BY PaymentMethod
ORDER BY Total_Orders DESC;

### Online Orders
```sql
SELECT *
FROM sales_data
WHERE PaymentMethod = 'Online';
