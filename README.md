# Amazon Product Review Analysis.
A Comprehensive Data Analysis for E-Commerce Optimization Powered by  RetailTech Insights

## Project Overview
This project aims to generate data-driven recommendations from product listings and customer feedback on Amazon, helping guide product improvement, marketing strategy, and customer engagement tactics.

## Data Source
This data was scraped from Amazon product pages with a total of 1,465 rows and 16 columns.
* **Product details:**
   * Product_id
   * Product_name
   * Category
   * Actual_price
   * About_product
* **Discount details:**
   * Discounted_price
   * Discount_percentage
* **Customer data:**
  * User_id
  * User_name
* **Ratings and Review**

## Tools Used and Their Purpose
* **Microsoft Excel:** Data cleaning, calculations, pivot tables, chart creation.
* **PivotTables:** Aggregating data for reviews, discounts, ratings, and price comparisons.
* **Excel Formulas:** Derived metrics like Number of Review, Price Range Buckets, Discount Bucket, Potential revenue, 50% Discount marker.
* **Excel Charts & Slicers:** Visualization and dynamic filtering in the dashboard.
  
## Exploratory Data Analysis (EDA)
### Data Cleaning & Preparation
The EDA focused on understanding the structure, completeness, and key distributions within the dataset. The steps included:
* **Data Structure Audit:** The presence of 1,465 rows and 16 columns covering product names, categories, prices, discounts, ratings, and review information was verified.
* **Missing Values:** Removed blank and irrelevant entries e.g., NULL, missing prices and invalid data entry under rating.
* **Duplicates:** Removed duplicate product_ids
* **Data Type Conversion:** Converted pricing and rating fields from general to currency and numerical formats for accurate calculation.
* **Category Cleaning:** Extracted top-level/main product categories from multi-tiered category strings to allow consistent grouping.
* **Product Cleaning:** Shortened product name.

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

## Data Analysis
Using Excel PivotTables, calculated fields, and chart visualizations, the following key analyses were performed:

1. **Average Discount Percentage by Category:** Identified product category HomeImprovement with the highest average discounts percentage.

2. **Product Count by Category:** Revealed that Electronics, Home&Kitchen, Computers&Accessories are the most saturated categories in decreasing order.

3. **Total Reviews per Category:** Highlighted customer engagement levels across product categories with Electronics, Home&Kitchen, Computers&Accessories having the most engagements.

4. **Highest Average Ratings:** Most of the top-rated products are computer accessories and home&kitchen appliances.

5. **Price Comparison (Actual vs Discounted):** Found major price reductions in product category Electronics.

6. **Most Reviewed Products:** The most reviewed products are boAT, Samsung and Zebronics which are under the categories Computers&Accessories and Electronics.

7. **50%+ Discount Products:** Identified a significant count of products marketed with discounts of 50% or more (660 products), however products with <50% were more (688 products).

8. **Rating Distribution:** Found most products fall between 4.0–4.3, indicating generally favorable customer feedback.

9. **Potential Revenue by Category:** Calculated as Actual Price × Rating Count, showing revenue dominance by high-value categories Electronics, Computers&Accessories, Home&Kitchen with most number of reviews.

10. **Price Range Buckets:** Most products were priced in the >₹500 range, indicating a top-tier market focus.

11. **Rating vs Discount Relationship:** Revealed a weak relationship between heavy discounts and product rating with rating reducing with increase in dicount bucket. this shows discounts don’t always improve customer ratings.

12. **Products with <1,000 Reviews:** 307 products fall in the 0–999 reviews range while a large number of products receive very few reviews

13. **Top Discounted Categories:** Computers&Accessories led in aggressive pricing discount strategies.

14. **Top 5 Products by Rating Score:** A composite metric (Rating × Number of Review) highlighted the top 5 highest-performing products across both dimensions as boAT, Samsung, AmazonBasics, Zebronics and Bajaj in descending order. These products are under the categories Computer&Accessories, Electronics and Home&Kitchen.

## Dashboard Highlights
* **Dashboard title: Amazon Product Review Insight Dashboard**
* Used slicers for Product Category, Discount Bucket, Rating and Price Range Bucket
* Created 14 distinct charts:
Column, Line, Bar, Pie, Area and Combo
* Organized with consistent layout and labeled headers

## Recommendations for Product Improvement, Marketing, and Customer Engagement

1. **Focus on High-Performing Categories**  
   Electronics, Home & Kitchen, and Computers & Accessories consistently top product count, reviews, and revenue potential. Prioritize these categories for new product launches, detailed competitive analysis, and optimized advertising.

2. **Refine Discount Strategies for Maximum Impact**  
   While Electronics sees significant price reductions, data shows **no strong correlation between higher discounts and better ratings**. Avoid deep discounts unless they’re part of broader campaigns; instead, emphasize product quality and reviews to drive conversion.

3. **Leverage Top Brands and Products**  
   Highlight and promote best-rated and most-reviewed brands like **boAT, Samsung, Zebronics, AmazonBasics, and Bajaj**. These drive trust and engagement—ideal for bundling, cross-selling, and sponsored placements.

4. **Optimize for Review Generation**  
   A substantial number of products (307) have fewer than 1,000 reviews. Invest in post-purchase review campaigns, follow-ups, and review incentives to boost social proof, especially for newer or underperforming SKUs.

5. **Target Premium Segments Thoughtfully**  
   With most products priced above ₹500, tailor your marketing and messaging toward premium customers. Ensure value propositions (durability, features, brand trust) are clearly communicated in listings and ads.

6. **Promote Products from Well-Rated Subcategories**  
   Products in categories like **Computer Accessories** and **Home & Kitchen Appliances** have some of the highest customer ratings. Focus on promoting these products more, and consider adding similar items to your catalog that match their quality and customer appeal.

7. **Stand Out in Crowded Categories**  
   Categories like **Electronics** are very competitive but also receive the most customer attention. To succeed here, highlight what makes your product different—such as unique features, better quality, or additional services like free installation or extended warranties.

8. **Be Cautious with Heavy Discounts**  
   Over 660 products have discounts over 50%, but many of these may not be profitable or performing well. Instead of always using large discounts, try limited-time deals, bundle offers, or loyalty programs to attract buyers while protecting profit margins.

9. **Monitor and Adjust Rating Trends**  
   With most products rated between 4.0–4.3, maintain a strong focus on customer service, shipping experience, and accurate product descriptions to prevent dips below this favorable range.

10. **Boost Discovery of High Potential Products**  
    Use the **Rating × Review count metric** to continuously identify rising stars. Prioritize these in email campaigns, homepage spots, and seasonal promotions.

## Limitations & Assumptions


- **Assumed Revenue Calculation:**  
  Potential revenue was estimated using `Actual Price × Rating_Count`. This does not account for product returns, abandoned carts, or discounts actually applied at checkout.

- **Discount Interpretation:**  
  Discount percentages were taken at face value without validating real-time market price changes or time-limited promo codes.

- **Static Snapshot:**  
  Data reflects a specific point in time. Seasonal trends, flash sales, and new product launches may impact future performance and should be monitored continuously.


## Next Steps / Further Analysis

1. **Time-Series Analysis:**  
   Study product performance trends over time to identify seasonality, promotional impact, and lifecycle phases.

2. **Sentiment Analysis on Reviews:**  
   Perform text analysis on customer reviews to uncover recurring themes, complaints, or feature requests for product improvement.

3. **Analyze Profitability of Discounted Products:**
Add cost information to see if heavily discounted products are still making a profit. This helps decide if offering big discounts is a good long-term strategy.

5. **Customer Segmentation:**  
   Group buyers based on product preferences, price sensitivity, and review behavior to guide personalized marketing strategies.

6. **Ad Performance Integration:**  
   Combine data with ad impressions, click-through rates (CTR), and conversions to understand what’s driving traffic and revenue beyond organic performance.

7. **Competitor Benchmarking:**  
   Compare top products and brands against similar listings to understand what’s winning in saturated categories like Electronics.

8. **Review Growth Tracking:**  
   Monitor how quickly products accumulate reviews after launch to estimate product visibility and customer engagement.






