Project Overview

This project analyzes sales, customers, and product performance using SQL.
The goal is to generate business insights such as revenue trends, customer segmentation, product performance, and category contribution.

The analysis is built using SQL queries and views on a dataset containing:

fact_sales

dim_products

dim_customers

The project demonstrates advanced SQL analytics techniques, including:

Time-based analysis

Window functions

Customer segmentation

Product performance metrics

Cumulative analysis

Business KPI calculations

📂 Dataset Structure
1️⃣ fact_sales

Contains transaction-level sales data.

Column	Description
order_number	Unique order ID
order_date	Date of purchase
product_key	Product identifier
customer_key	Customer identifier
sales_amount	Total sale value
quantity	Quantity purchased
price	Price per unit
2️⃣ dim_products

Contains product information.

Column	Description
product_key	Product identifier
product_name	Name of product
product_number	Product code
category	Product category
subcategory	Product subcategory
cost	Product cost
3️⃣ dim_customers

Contains customer demographic data.

Column	Description
customer_key	Customer ID
customer_number	Customer number
first_name	Customer first name
last_name	Customer last name
birthdate	Customer birth date
📈 Key Analysis Performed
1️⃣ Sales Trend Analysis

Analyzes how sales evolved over time.

Yearly Sales

Total sales per year

Total customers per year

Identifies growth trends

Example insights:

Sales increased from 2010 to 2013

2013 was the peak year

Sales declined slightly in 2014

2️⃣ Monthly Sales Analysis

Tracks monthly revenue performance.

Key metrics:

Monthly sales

Monthly customer count

Uses:

DATE_FORMAT(order_date,'%Y-%m')

to group sales by month.

📊 Cumulative Analysis

Cumulative analysis helps measure business growth over time.

Running Total Sales

Calculates cumulative revenue by month using window functions.

Example:

SUM(total_sale) OVER (ORDER BY month_wise)

This shows:

how revenue accumulates

long-term growth trends

Moving Average

Calculates moving average sales by year.

AVG(avg_price) OVER(ORDER BY year_wise)

Helps smooth out sales fluctuations.

📉 Product Performance Analysis

Analyzes how each product performs yearly.

Metrics calculated:

Current year sales

Average sales per product

Previous year sales

Sales growth or decline

Window functions used:

AVG() OVER(PARTITION BY product_name)
LAG()

Key insights:

Identifies products performing above or below average

Detects year-over-year sales changes

🧩 Category Contribution Analysis

Determines which product categories contribute most to total revenue.

Formula used:

(category_sales / total_sales) * 100

Output includes:

Category

Total Sales

Percentage contribution

Example insight:

Bike category contributes the highest revenue

Business dependency on a single category can increase risk.

📦 Product Cost Segmentation

Products are grouped into cost ranges:

Cost Range	Description
0–1000	Low cost products
1000–2000	Mid-range products
Above 2000	Premium products

This helps understand product distribution by price level.

👥 Customer Segmentation

Customers are classified into three segments based on spending and purchase history.

Segment	Criteria
VIP	Lifespan ≥ 12 months AND spending > 5000
Regular	Lifespan ≥ 12 months AND spending ≤ 5000
New	Lifespan < 12 months

Metrics used:

total spending

first order date

last order date

customer lifespan

📑 Customer Analytics Report

A SQL View called:

dataset.final_report

was created to consolidate customer insights.

Metrics included
Metric	Description
Total Orders	Number of orders
Total Sales	Total spending
Total Quantity	Items purchased
Total Products	Unique products purchased
Lifespan	Customer relationship duration
Recency	Months since last purchase
Avg Order Value	Revenue per order
Avg Monthly Spend	Spending per month
Additional segmentation

Customers are also grouped by age groups:

Age Group
Under 20
20–29
30–39
40–49
50+
📦 Product Analytics Report

A second SQL view was created:

dataset.product_report_1

This report aggregates product-level metrics.

Product Metrics
Metric	Description
Total Orders	Number of orders
Total Sales	Revenue generated
Total Quantity	Units sold
Total Customers	Unique buyers
Lifespan	Sales duration
Recency	Months since last sale
Avg Selling Price	Avg price per unit
Avg Order Revenue	Revenue per order
Avg Monthly Revenue	Revenue per month
🏷 Product Performance Segmentation

Products are classified into revenue segments.

Segment	Criteria
High Performer	Sales > 50,000
Mid Range	Sales between 10,000–50,000
Low Performer	Sales < 10,000

This helps identify:

top performing products

products needing improvement

🧠 SQL Concepts Used

This project demonstrates the use of:

CTEs (Common Table Expressions)

Window Functions

LAG()

AVG() OVER()

SUM() OVER()

Date functions

Aggregation

Customer segmentation

Product segmentation

Business KPI calculations

🛠 Tools Used

SQL (MySQL)

Relational Database

GitHub for version control

🚀 Future Improvements

Possible enhancements:

Create Power BI / Tableau dashboards

Build customer churn prediction

Perform RFM analysis

Develop product recommendation models

👨‍💻 Author

Abhishek Bains

Data Analyst | SQL | Python | Power BI | Tableau

Currently working on data analytics and business intelligence projects.

