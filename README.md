# Financial Performance Dashboard

## Objective
Develop an end-to-end financial dashboard using PostgreSQL and Power BI to analyse sales performance, profitability, discount impact and regional trends.

## Tools
- PostgreSQL
- SQL
- Power BI
- Power Query
- Git/GitHub
- Excel

## Dataset
Sample Superstore Dataset

## Project Progress

### Completed
- [x] Created GitHub repository
- [x] Designed project structure
- [x] Installed PostgreSQL 17
- [x] Created `financial_dashboard` database
- [x] Created `superstore` table
- [x] Imported 9,994 records into PostgreSQL
- [x] Performed initial SQL validation using `COUNT(*)`

### In Progress
- [ ] Exploratory SQL analysis
- [ ] Power BI dashboard development
- [ ] Business insights and recommendations
- [ ] README documentation improvements

## Project Structure

financial-dashboard-powerbi/
├── data/
│ ├── raw/
│ └── cleaned/
├── sql/
├── dashboard/
├── images/
└── README.md

## SQL Analysis

## Sales by Category
The initial SQL exploration identified Thechnology as the top-performing category in terms of sales

Category	Total Sales
Technology	836,154.03
Furniture	741,999.80
Office Supplies	719,047.03

SQL Query

SELECT category,
       ROUND(SUM(sales),2) AS total_sales
FROM superstore
GROUP BY category
ORDER BY total_sales DESC;

Query Result

![Sales by Category Query](images/sales_by_category_query.png)