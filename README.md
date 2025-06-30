![image](https://github.com/user-attachments/assets/085d1b89-1833-4106-98f8-e169c8937e64)# Amazon-Product-Review-Analysis.
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
## Data Analysis

Using Excel PivotTables, calculated fields, and chart visualizations, the following key analyses were performed:
1. Average Discount Percentage by Category: Identified product category HomeImprovement with the highest average discounts percentage.
2. Product Count by Category: Revealed that Electronics, Home&Kitchen, Computers&Accessories are the most saturated categories in decreasing order.
3. Total Reviews per Category: Highlighted customer engagement levels across product categories with Electronics, Home&Kitchen, Computers&Accessories having the most engagements.
4. Highest Average Ratings: Most of the top-rated products are computer accessories and home&kitchen appliances.
5. Price Comparison (Actual vs Discounted): Found major price reductions in product category Electronics.
6. Most Reviewed Products: The most reviewed products are boAT, Samsung and Zebronics which are under the categories Computers&Accessories and Electronics.
7. 50%+ Discount Products: Identified a significant count of products marketed with discounts of 50% or more (660 products), however products with <50% were more (688 products).
8. Rating Distribution: Found most products fall between 4.0–4.3, indicating generally favorable customer feedback.
9. Potential Revenue by Category: Calculated as Actual Price × Rating Count, showing revenue dominance by high-value categories Electronics, Computers&Accessories, Home&Kitchen with most number of reviews.
10. Price Range Buckets: Most products were priced in the >₹500 range, indicating a top-tier market focus.
11. Rating vs Discount Relationship: Revealed a weak relationship between heavy discounts and product rating with rating reducing with increase in dicount bucket. this shows discounts don’t always improve customer ratings.
12. Products with <1,000 Reviews: 307 products fall in the 0–999 reviews range while a large number of products receive very few reviews
13. Top Discounted Categories: Accessories & Cable segments led in aggressive pricing strategies.
14. Top 5 Products by Combined Score: A composite metric (Rating × Review Count) highlighted the top 5 highest-performing products across both dimensions.
16. The cleaned and enhanced dataset had a total 1348 rows and 23 columns which enabled deeper statistical and business analysis, as well as visual storytelling through PivotTables and charts.

