# Customer_Behaviour_Analysis
To analyze customer shopping behavior using Python, MySQL, Power BI, and Excel to identify purchasing patterns, customer preferences, product performance, and revenue trends.
Customer Behavior Analytics
Overview

Customer Behavior Analytics is an end-to-end data analytics project focused on understanding customer purchasing patterns, product performance, customer demographics, revenue contribution, reviews, discounts, and subscription behavior.

The project demonstrates the complete analytics workflow — from data loading and cleaning to SQL analysis, Power BI visualization, reporting, and presentation.

Key Objectives
Analyze customer purchasing behavior
Identify high-performing products and categories
Understand customer demographics and revenue contribution
Compare subscribed and non-subscribed customers
Analyze repeat customer behavior
Evaluate discounts and purchasing patterns
Build an interactive Power BI dashboard
Generate actionable business insights
Dataset

The project uses a customer transaction dataset containing information such as:

Customer ID
Age
Gender
Item Purchased
Category
Purchase Amount
Review Rating
Discount Applied
Previous Purchases
Subscription Status
Other customer and transaction attributes

The dataset was initially loaded and explored using Python and Pandas.

Tools & Technologies
Tool	Purpose
Python	Data loading, cleaning and EDA
Pandas	Data manipulation
NumPy	Numerical analysis
Matplotlib / Seaborn	Exploratory visualizations
MySQL / PostgreSQL / SQL Server	SQL-based data analysis
Power BI	Interactive dashboard
Gamma	Presentation/PPT creation
Excel / CSV	Dataset handling
Project Workflow
Dataset
   ↓
Python & Pandas
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
SQL Analysis
   ↓
Power BI Dashboard
   ↓
Business Insights & Report
   ↓
Gamma Presentation
1. Data Loading

The dataset was imported into Python using Pandas.

import pandas as pd

df = pd.read_csv("customer_data.csv")

print(df.head())
print(df.shape)
print(df.info())

Initial analysis was performed to understand the dataset structure, columns, data types, and number of records.

2. Exploratory Data Analysis

EDA was performed to understand customer behavior and identify patterns.

Key EDA Activities
Dataset shape and structure
Data type analysis
Missing value detection
Duplicate detection
Descriptive statistics
Distribution analysis
Categorical variable analysis
Correlation analysis
Outlier identification

Example:

df.describe()
3. Data Cleaning

The dataset was cleaned before performing SQL analysis and visualization.

Cleaning Activities
Handled missing values
Removed duplicate records
Corrected data types
Standardized categorical values
Checked inconsistent values
Validated numerical columns
Prepared clean data for database loading

Example:

df = df.drop_duplicates()

df.isnull().sum()
4. SQL Analysis

The cleaned dataset was loaded into a relational database and analyzed using SQL.

The project can be implemented using:

MySQL
PostgreSQL
SQL Server
Example Business Questions
Revenue by Gender
SELECT 
    gender,
    SUM(purchase_amount) AS total_revenue
FROM customer
GROUP BY gender;
Top 5 Products by Average Rating
SELECT 
    item_purchased,
    AVG(review_rating) AS average_product_rating
FROM customer
GROUP BY item_purchased
ORDER BY average_product_rating DESC
LIMIT 5;
Repeat Buyers and Subscription Behavior
SELECT
    CASE
        WHEN previous_purchases > 5 THEN 'Repeat Buyers'
        ELSE 'Other Customers'
    END AS customer_type,
    COUNT(*) AS total_customers,
    SUM(
        CASE
            WHEN subscription_status = 'Yes' THEN 1
            ELSE 0
        END
    ) AS subscribed_customers
FROM customer
GROUP BY customer_type;
Revenue Contribution by Age Group

Age groups were created and analyzed to understand which customer segments contribute the most revenue.

5. Power BI Dashboard

An interactive Customer Behavior Dashboard was created using Power BI.

Dashboard KPIs
Average Purchase Amount
Average Review Rating
Total Customers
Subscription Rate
Total Revenue
Repeat Customers
Dashboard Analysis

The dashboard provides insights into:

Customer subscription behavior
Revenue trends
Product performance
Customer demographics
Purchase patterns
Category-level performance
Review ratings

The dashboard was designed with interactive visuals and filters to make customer insights easy to understand.

6. Results & Insights

The analysis helps identify important customer behavior patterns, including:

Customer purchasing trends
High-performing products
Product rating patterns
Revenue contribution across customer segments
Subscription behavior
Repeat customer patterns
Category-level performance
Demographic-based purchasing behavior

These insights can help businesses improve customer retention, product strategy, marketing campaigns, and revenue generation.

Note: Exact numerical findings should be updated based on the final dataset and Power BI results.

7. Report

A detailed project report was prepared covering:

Introduction
Problem Statement
Objectives
Dataset Description
Data Cleaning
Exploratory Data Analysis
SQL Analysis
Power BI Dashboard
Key Findings
Business Recommendations
Conclusion
8. Presentation

A professional project presentation was created using Gamma.

The presentation covers:

Project Overview
Business Problem
Dataset
Methodology
Data Cleaning
EDA
SQL Analysis
Power BI Dashboard
Key Insights
Recommendations
Conclusion
9. Project Structure
Customer-Behavior-Analytics/
│
├── dataset/
│   └── customer_data.csv
│
├── python/
│   ├── data_loading.py
│   ├── data_cleaning.py
│   └── eda.py
│
├── sql/
│   └── customer_analysis.sql
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
├── report/
│   └── customer_behavior_report.pdf
│
├── presentation/
│   └── customer_behavior_presentation.pdf
│
├── screenshots/
│   └── dashboard.png
│
└── README.md
How to Run
Step 1 — Clone the Repository
git clone <your-github-repository-url>
cd Customer-Behavior-Analytics
Step 2 — Install Python Libraries
pip install pandas numpy matplotlib seaborn sqlalchemy pymysql

For PostgreSQL:

pip install psycopg2-binary
Step 3 — Load the Dataset

Place the dataset inside:

dataset/customer_data.csv

Then run the Python scripts for data loading, cleaning, and EDA.

Step 4 — Set Up Database

Create a database using MySQL, PostgreSQL, or SQL Server.

Example for MySQL:

CREATE DATABASE customer_behaviour;

Load the cleaned dataset into the database and execute the SQL queries from:

sql/customer_analysis.sql
Step 5 — Open Power BI

Open:

powerbi/customer_behavior_dashboard.pbix

Update the database connection if required and refresh the data.

Step 6 — View Report & Presentation

The project report and Gamma-generated presentation are available in:

report/
presentation/
Key Skills Demonstrated

Python | Pandas | NumPy | EDA | Data Cleaning | SQL | MySQL | PostgreSQL | SQL Server | Power BI | Data Visualization | Business Analytics | Reporting | Presentation
Conclusion

This project demonstrates an end-to-end data analytics workflow, transforming raw customer transaction data into meaningful business insights through Python, SQL, and Power BI.
