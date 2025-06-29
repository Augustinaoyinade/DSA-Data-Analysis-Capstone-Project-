# Amazon-Product-Review-Analysis.
A Comprehensive Data Analysis for E-Commerce Optimization Powered by  RetailTech Insights
## Project Overview
This project aims to generate data-driven recommendations from product listings and customer feedback on Amazon, helping guide product improvement, marketing strategy, and customer engagement tactics.
## Data Source
This data was scraped from Amazon product pages with a total of 1,465 rows and 16 columns.
* Product details:
   * Product_id
   * Product_name
   * Category
   * Actual_price
   * About_product
* Discount details
   * Discounted_price
   * Discount_percentage
* Customer data
  * User_id
  * User_name
* Ratings and Review
## Tools Used and Their Purpose
* Microsoft Excel: Data cleaning, calculations, pivot tables, chart creation
* PivotTables: Aggregating data for reviews, discounts, ratings, and price comparisons
* Excel Formulas: Derived metrics like Review Count, Price Buckets, Discount Flags
* Excel Charts & Slicers: Visualization and dynamic filtering in the dashboard
## Exploratory Data Analysis (EDA)
### Data Cleaning & Preparation
The EDA focused on understanding the structure, completeness, and key distributions within the dataset. The steps included:
* Data Structure Audit: The presence of 1,465 rows and 16 columns covering product names, categories, prices, discounts, ratings, and review information was verified.
* Missing Values: Removed blank and irrelevant entries e.g., NULL, missing prices and invalid data entry under rating.
* Data Type Conversion: Converted pricing and rating fields from general to currency and numerical formats for accurate calculation.
* Category Cleaning: Extracted top-level/main product categories from multi-tiered category strings to allow consistent grouping.
* Product Cleaning: Shortened product name.
### Derived Fields: Created several new columns including:



The cleaned and enriched dataset enabled deeper statistical and business analysis, as well as visual storytelling through PivotTables and charts.

