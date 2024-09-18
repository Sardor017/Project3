AdventureWorks2022 Dashboard

Overview

The AdventureWorks2022 Dashboard is designed to provide comprehensive insights into the business operations of AdventureWorks, covering human resources, sales, and purchasing activities. This dashboard leverages data from multiple tables within the AdventureWorks2022 database to help stakeholders analyze employee performance, sales trends, order details, and purchasing history.

Data Sources
The dashboard pulls data from the following key areas:

Human Resources (HR)

Employee details such as organization level, job title, birth year, hire date, and salary history.
Department information including department name, group, and shift details.
Sales

Sales order details, including product, category, and pricing information.
Sales person performance, covering quotas, bonuses, and commission details.
Sales territories with grouping by regions and territories.
Purchasing

Purchase order details with vendor and shipping method data.
Financial information such as subtotal, tax, freight, and total due for each purchase order.
Key Metrics and Insights
The dashboard covers a variety of metrics, offering insights across the following dimensions:

1. Employee Metrics
Job Title and Department Information: Provides a breakdown of employees by job title, department, and group.
Hire Date and Employment History: Tracks employee tenure and employment start/end dates.
Salaried and Hourly Employees: Analysis of salaried versus non-salaried employees, including vacation and sick leave usage.
Pay History: Displays employee pay rates and frequency.
2. Sales Performance
Order Details: Includes order date, due date, ship date, and the associated salesperson for each order.
Product Information: Lists product details, including name, number, model, and category.
Sales Financials: Tracks total due, tax, freight, and commission amounts for each order.
Territory Insights: Groups sales data by territory and territory group, providing a regional breakdown of sales performance.
Sales Reason Aggregation: Groups all sales reasons related to an order for a consolidated view.
3. Purchasing Data
Vendor Information: Displays vendor names, credit ratings, and associated purchase orders.
Purchase Order Breakdown: Provides details on purchase order quantities, unit prices, and total line amounts.
Shipping Details: Includes information on the shipping method, rates, and base shipping charges.
Data Structure and Queries
The dashboard is built on SQL queries that utilize Common Table Expressions (CTEs) to structure data across multiple tables. The key queries include:

Employee Data: A CTE that joins employee information with pay history and department history, providing a comprehensive view of each employee's details.
Sales Order Data: Another CTE that aggregates sales order details with product, category, and territory information.
Purchase Order Data: A final query that links purchase order headers with vendor details, shipping methods, and line item information.
Usage
Employee Performance Analysis: Users can explore employee metrics like tenure, department affiliation, pay rates, and leave balances.
Sales Tracking: The dashboard offers detailed tracking of sales performance by region, product, and salesperson, including financial summaries like total sales, tax, and freight.
Purchasing Overview: Users can analyze purchasing patterns, vendor performance, and shipment details to optimize procurement processes.
How to Use
Filter by Date: The dashboard allows filtering by sales and purchase order dates, enabling analysis for specific time periods.
Product and Category Filters: Filter sales by product name, category, or model for a more focused analysis.
Territory Filter: View sales performance by specific territories or groups for regional insights.
Employee Drill-Down: Drill down into employee data to view detailed histories and performance metrics.
Future Improvements
Potential enhancements for the dashboard include:

Adding real-time data integration for more up-to-date reporting.
Including additional KPIs for vendor performance and procurement efficiency.
Developing predictive models for sales and hiring trends.	
