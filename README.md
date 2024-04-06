# Superstore Sales Anaysis

## Table of Contents

- [Project Overview](#project-overview)
- [Recommendations](#recommendations)
- [Data Soursces](#data-sources)
### Project Overview

This data analysis project aims to provide insights into the sales performance of a supply chain company over a four year period. By analysing various aspects of the sales data, we seek to identify trends, make data-driven recommendations, and gather a deeper understanding of the company's performance.

### Data Sources

Sales Data: The primary dataset used for this analysis is the 'superstore.csv' file, containing comprehensive collection of sales, customer, and product data about each sale made by the company.

### Tools

- Excel - Data Cleaning [Download here]()
- SQL Server - Data Analysis
- PowerBI - Creating Reports


### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis

EDA involved exploring the sales data to answer key questions such as:

- Perform descriptive statistics to understand the distribution of sales, quantity, discount, and profit.
- Identify top-selling products, categories, and sub-categories.
- Explore sales trends over time, including seasonality and year-over-year growth.
- Analyse the impact of discounts on sales and profitability.

### Data Analysis

Calculate RFM Metrics:

```sql
WITH customer_rfm AS
(
 SELECT 
        [Customer ID],
        DATEDIFF(MONTH, MAX([Order Date]), MIN([Order Date])) AS Recency,
        COUNT(DISTINCT [Order ID]) AS Frequency,
        SUM(Sales) AS Monetary_Value
    FROM 
        Orders
    GROUP BY 
        [Customer ID]
)
SELECT 
	[Customer ID],
	Recency,
	Frequency,
	Monetary_Value
FROM 
   customer_rfm 
ORDER BY 4 DESC
```

### Results/Findings

1.
2.

### Recommendations 

Based on the analysis, we recommend the following actions:



#### Limitations


### References

