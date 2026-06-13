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
- [x] Exploratory SQL analysis

### In Progress
- [ ] Power BI dashboard development
- [ ] Create KPIs for sales, profits, discounts and volume
- [ ] Build regional and category performance visualisation
- [ ] Translate SQL findings into business-focused dashboard insights
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

## Data Quality Assessment

Before conducting the analysis, the dataset was assessed to ensure its suitability for business analysis.
The following checks were performed:

- Missing values assessment
- Duplicate records assessment
- Dataset temporal coverage validation

### Results

| Validation Check  | Result |
| Missing values    | No missing values identified |
| Duplicate records | No duplicate records identified |
| Date range        | Dataset covers the period from 2014 to 2017 |

The dataset was considered suitable for further analysis without requiring additional cleaning steps.

### SQL Validation

#### Null Values Check
![Null check](images/check_null_query.png)

#### Duplicate Records Check
![Duplicate check](images/duplicate_check.png)

#### Date Range Validation
![Date range check](images/date_range_check.png)

## Exploratory SQL Analysis

### Profit by Category

Technology generated the highest profit ($145,544.95), followed by Office Supplies ($122,490.80).
Although Furniture represented one of the highest sales categories, it produced substantially lower profits ($18,451.27), suggesting potential margin challenges or the impact of discounts.

![Profit by Category](images/profit_by_category_query.png)

### Impact of Discounts on Profitability

An analysis of average profit by discount level revealed that small discounts (10%) were associated with higher average profits.
However, discount levels above 30% resulted in negative average profits, suggesting that aggressive discount strategies may significantly reduce overall profitability.

![Discount vs Profit](images/discount_vs_profit_query.png)

### Regional Profit Analysis

The West region generated the highest total profit, followed by the East region.
Although all regions remained profitable, the Central region significantly underperformed compared with the top-performing regions, suggesting opportunities for further investigation into product mix, discount strategies, or regional sales performance.

![Profit by Region](images/profit_by_region_query.png)

## Regional Discont Analysis 

The Central region exhibited the highest average discount rate (24%), while the West region maintained the lowest average discount level (11%).
This finding suggests that discount strategies may be contributing to the lower profitability observed in the Central region.

![Discont by Region](images/discont_by_region_query.png)

## Category Performande whitin Regions

A deeper investigation revealed that Furniture generated negative profits in the Central region (-$2,871.05), while Technology remained the strongest contributor to profitability across all regions.
These findings indicate that the combination of high discount levels and underperforming product categories may be reducing the Central region's overall profitability.

![Profit by Region by Category](images/profit_region_by_category_query.png)

## Key Findings

- Technology was the most profitable category overall.
- Discounts above 30% were associated with negative average profits.
- The West region achieved the highest profitability while maintaining the lowest average discount rate.
- The Central region showed the weakest performance and the highest average discount levels.
- Furniture operated at a loss within the Central region, highlighting a potential opportunity for strategic review.