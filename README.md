# SQL_Data_Analysis_Project

🛒 Zepto Inventory Analysis (SQL Project)

📌 Project Overview

This project simulates a real-world e-commerce data analytics workflow using SQL. It demonstrates how data analysts in retail or marketplace environments work behind the scenes to structure messy catalog data, clean inconsistencies, and extract business insights.

The primary objectives were to:

Build a structured PostgreSQL inventory database

Perform Exploratory Data Analysis (EDA)

Clean and transform pricing data

Write business-driven SQL queries for actionable insights

The dataset was sourced from Kaggle and originally scraped from Zepto’s product listings, reflecting a real-world e-commerce inventory system.



# Dataset Overview

Each record represents a unique SKU (Stock Keeping Unit). Duplicate product names may exist because the same product appears in different weights, quantities, discounts, or packaging formats — similar to real e-commerce catalogs.


# Column Descriptions

Column	- Description

sku_id	- Synthetic primary key

name	- Product name as displayed in the app

category	- Product category (Fruits, Snacks, Beverages, etc.)

mrp -	Maximum Retail Price (converted from paise to ₹)

discountPercent	- Discount applied on MRP

discountedSellingPrice	- Final selling price after discount (₹)

availableQuantity	- Units available in inventory

weightInGms	- Product weight in grams

outOfStock	- Boolean flag indicating stock availability

quantity	- Number of units per package



# Tech Stack

PostgreSQL – Database management and querying

pgAdmin – Data import and management

SQL – Data cleaning, transformation, and analysis



🔧# Project Workflow

* Database & Table Creation*

A structured table was created with appropriate data types to support analytical queries:


CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);




** 2 Exploratory Data Analysis (EDA)**

Performed structured analysis to understand dataset integrity and structure:

Counted the total number of records

Sampled dataset to inspect schema and content

Checked for null values across columns

Identified distinct product categories

Compared in-stock vs out-of-stock counts

Detected duplicate product names with different SKUs

This step ensured clarity before proceeding to transformations.



** 3. Data Cleaning & Transformation**

To ensure accurate business reporting:

Removed rows where mrp or discountedSellingPrice = 0

Converted pricing columns from paise to rupees

Standardized numeric precision

Validated inventory and discount consistency

This improved data reliability for downstream analysis.



** 4.  Business-Driven SQL Analysis**

The following analytical queries were executed:

Top 10 best-value products based on discount percentage

High-MRP products are currently out of stock

Estimated potential revenue by product category

Expensive products (MRP > ₹500) with minimal discount

Top 5 categories with the highest average discounts

Price-per-gram calculation for value comparison

Weight-based segmentation (Low, Medium, Bulk)

Total inventory weight per product category

These insights simulate real retail analytics use cases such as pricing optimization, inventory control, and revenue analysis.


📊#  Key Outcomes

Built a clean and query-ready e-commerce inventory database

Applied structured SQL for exploratory and business analysis

Converted raw scraped pricing data into an analytical format

Simulated real-world catalog and pricing intelligence workflows




**🚀 How to Run the Project**

Install PostgreSQL and pgAdmin

Clone this repository

Create the database

Run the table creation script

Import the dataset into the Zepto table

Execute SQL queries provided in the repository

Review query outputs for business insights



**📌 Project Significance**

*This project demonstrates:

Practical SQL proficiency

Real-world data cleaning and transformation

Analytical thinking aligned with business problems

Understanding of e-commerce inventory systems

It reflects the day-to-day workflow of a data analyst working in retail or marketplace environments.*
