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
* Discount details:
   * Discounted_price
   * Discount_percentage
* Customer data:
  * User_id
  * User_name
* Ratings and Review
## Tools Used and Their Purpose
* Microsoft Excel: Data cleaning, calculations, pivot tables, chart creation.
* PivotTables: Aggregating data for reviews, discounts, ratings, and price comparisons.
* Excel Formulas: Derived metrics like Number of Review, Price Range Buckets, Discount Bucket, Potential revenue, 50% Discount marker.
* Excel Charts & Slicers: Visualization and dynamic filtering in the dashboard.
## Exploratory Data Analysis (EDA)
### Data Cleaning & Preparation
The EDA focused on understanding the structure, completeness, and key distributions within the dataset. The steps included:
* Data Structure Audit: The presence of 1,465 rows and 16 columns covering product names, categories, prices, discounts, ratings, and review information was verified.
* Missing Values: Removed blank and irrelevant entries e.g., NULL, missing prices and invalid data entry under rating.
* Duplicates: Removed duplicate product_ids
* Data Type Conversion: Converted pricing and rating fields from general to currency and numerical formats for accurate calculation.
* Category Cleaning: Extracted top-level/main product categories from multi-tiered category strings to allow consistent grouping.
* Product Cleaning: Shortened product name.
### Derived Fields: Created several new columns including:
* Potential revenue (actual_price × rating_count)
* Number of Review by splitting comma-separated Review IDs using excel function
  `=COUNTA(TEXTSPLIT(R2,,","))` where R is Review_ID.
* Price Range Bucket to categorize products into < ₹200, ₹200–₹500, and > ₹500 using excel function
  `=IF(F2<200," <₹200",IF(F2<=500,"₹200–₹500",">₹500"))` where F is Discounted_price.
* 50% Discount marker for products with ≥50% discount using excel function
  `=IF(J2>=50%,"50% or more","<50%")` where J is Discount_percentage.
* Discount bucket to categorize products into 0-25%, 26-50%, 51-75%, 76-100% using excel function
  `=IF(J2<=25%,"0-25%",IF(J2<=50%,"26-50%",IF(J2<=75%,"51-75%","76-100%")))` where J is Discount_percentage.

The cleaned and enhanced dataset had a total 1348 rows and 23 columns which enabled deeper statistical and business analysis, as well as visual storytelling through PivotTables and charts.

