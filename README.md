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





2) Predicting TotalDue in Sales Data
Overview
This project builds a model to predict the TotalDue for sales transactions using data from AdventureWorks2022 database. The data includes details on product sales, employee information, and sales territories. A pipeline of regression models, including Ridge, Lasso, Huber, and Linear Regression, was developed and stacked to improve prediction performance.

Key Steps in the Process:
Data Extraction: SQL queries are used to extract sales data from several tables in the database.
Data Cleaning: The data is cleaned by converting text to numeric types and creating new features such as PriceDifference.
Feature Engineering:
Ordinal encoding is applied to categorical features (e.g., TerritoryName, ProductCategoryName) based on their relationship with TotalDue.
Polynomial features are generated for better model fitting.
Model Training: Multiple regression models are trained and stacked, with Huber Regressor as the final model.
Evaluation: Metrics such as MAE (Mean Absolute Error), MedAE (Median Absolute Error), and R² score are used to evaluate the model's performance.
Feature Importance: Feature importance is analyzed using a Random Forest model.
Files
SQL Query: The provided SQL query extracts and joins data from various tables in the AdventureWorks2022 database, creating a dataset used for training the model.
Data Cleaning & Feature Engineering: The code handles missing values, converts data types, and adds new features such as PriceDifference (the difference between ListPrice and StandardCost).
Modeling Pipeline: A machine learning pipeline that includes:
Ridge Regression with polynomial features (degree 6)
Lasso Regression with polynomial features (degree 4)
Huber Regression with polynomial features (degree 3)
Linear Regression with polynomial features (degree 5)
Stacking Regressor: A stacked regressor that combines the predictions of all the individual models, using Huber Regressor as the final model.
Evaluation: Metrics are calculated to assess the performance of the model.
Libraries Used
pandas: Data manipulation and analysis.
sklearn: Machine learning models and tools for feature scaling, regression, and cross-validation.
seaborn & matplotlib: Visualization of correlations and feature importance.
warnings: To ignore warning messages during model training.
Model Equation
After training, the model's equation is derived from the final Huber Regressor. The equation is constructed based on the learned coefficients and intercept:

y = intercept + coeff1*x1 + coeff2*x2 + ... + coeffN*xN
Where x1, x2, ..., xN are the features, and the coefficients indicate the strength of the relationship between each feature and the target (TotalDue).

Results
Metrics calculated from the model include:

MAE (Mean Absolute Error): A lower MAE indicates better performance in predicting actual values.
MedAE (Median Absolute Error): Measures the median magnitude of prediction errors.
R² Score: Explains how much variance in the dependent variable (TotalDue) is explained by the independent variables.
How to Run the Code
Install Dependencies: Ensure that the following libraries are installed using pip:

pip install pandas scikit-learn seaborn matplotlib
Data Preparation:

Use the SQL query to extract the data from AdventureWorks2022 database.
Save the data in CSV format (e.g., exam_model.csv).
Run the Script:

The script reads the CSV data, cleans it, creates new features, and trains the model.
The results, including evaluation metrics and feature importances, are displayed at the end.
Model Adjustment:

You can modify the degree of polynomial features or add more models to the stacking process for improved performance.
Future Enhancements
Hyperparameter Tuning: Fine-tuning the hyperparameters of the models using GridSearchCV or RandomizedSearchCV can improve model performance.
Feature Selection: Analyze and remove less important features to reduce model complexity.
Additional Models: Try adding other regression models like ElasticNet or Decision Trees to the stacking process.
Contact
For any questions or issues regarding the project, feel free to reach out!
