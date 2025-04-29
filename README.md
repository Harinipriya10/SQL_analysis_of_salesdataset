Sales Trend Analysis Using Aggregations on Chocolate Sales on 2022

Objective:
The objective of this project is to analyze monthly revenue and order volume from chocolate product sales data using SQL and visualize the trends using Python.

Tools Used:
MySQL– for data storage, querying, and aggregation
Python (Pandas, Matplotlib)* – for data cleaning and visualization
VS Code – as the code editor
Excel – for initial inspection (optional)

Dataset:
The dataset `chocolate_sales_dataset.csv` contains 1,094 records of chocolate product sales. It includes the following columns:

`Sales Person` – Name of the salesperson
`Country` – Country where the sale occurred
`Product` – Product type
`Date` – Date of sale
`Amount` – Revenue from the sale (in $)
`Boxes Shipped` – Quantity sold

Steps involved:

1. Data Cleaning
Converted `Amount` from string to numeric
Converted `Date` to datetime format
Removed any duplicate entries (if found)
Ensured all data types are appropriate

2. Loading into MySQL
A table named `chocolate_sales` was created
Data was imported using MySQL Workbench
Checked for successful insertion using `SELECT` statements
3. SQL Analysis
Aggregated monthly revenue and order volume using this query:

SQL Script:
SELECT 
    YEAR(Date) AS order_year,
    MONTH(Date) AS order_month,
    CONCAT(YEAR(Date), '-', LPAD(MONTH(Date), 2, '0')) AS year_month,
    SUM(Amount) AS total_revenue,
    COUNT(*) AS total_orders
FROM 
    chocolate_sales
GROUP BY 
    YEAR(Date), MONTH(Date)
ORDER BY 
    YEAR(Date), MONTH(Date);

Outcome:
Clear trends of sales and order volume were identified.
Growth spikes indicated potential promotional periods or seasonal effects.
Enabled better understanding of business cycles and performance over time.

Deliverables:
Cleaned dataset
SQL script for aggregation
Python visualization code
Final report (DOCX or PDF)
