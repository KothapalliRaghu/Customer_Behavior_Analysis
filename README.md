# Customer Shopping Behavior Analysis

An end-to-end data analytics project exploring customer shopping behavior using transactional data, combining **Python (EDA)**, **SQL (MS SQL Server)**, and **Power BI (dashboarding)** to uncover insights into spending patterns, customer segments, and subscription behavior.

## Project Overview

This project analyzes **3,900 customer transactions** across multiple product categories to answer key business questions around revenue drivers, discount behavior, customer segmentation, and product performance. The goal is to translate raw transactional data into actionable insights that support strategic business decisions.

## Dataset

| Detail | Description |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Demographics | Age, Gender, Location, Subscription Status |
| Purchase Details | Item Purchased, Category, Purchase Amount, Season, Size, Color |
| Shopping Behavior | Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type |
| Missing Data | 37 missing values in the `Review Rating` column |

## Tech Stack

- **Python** (pandas) — data cleaning, feature engineering, EDA
- **MS SQL Server** — structured business analysis via SQL
- **Power BI** — interactive dashboard for visual reporting

## Methodology

### 1. Data Preparation & Cleaning (Python)
- Loaded the dataset using `pandas`; explored structure with `df.info()` and `.describe()`
- Imputed missing `Review Rating` values using the **median rating per product category**
- Standardized column names to `snake_case`
- **Feature engineering:**
  - `age_group` — created by binning customer ages
  - `purchase_frequency_days` — derived from purchase frequency data
- Checked `discount_applied` vs. `promo_code_used` for redundancy and dropped the latter
- Loaded the cleaned dataset into **SQL Server** for downstream SQL analysis

### 2. Business Analysis (SQL)
Ten targeted queries were run against the cleaned data to answer key business questions:

1. **Revenue by Gender** — Male customers generated $157,890 vs. $75,191 from female customers
2. **High-Spending Discount Users** — Identified 839 customers who used discounts yet spent above the average purchase amount
3. **Top 5 Products by Rating** — Gloves, Sandals, Boots, Hat, Skirt
4. **Shipping Type Comparison** — Express shipping orders averaged $60.48 vs. $58.46 for Standard
5. **Subscribers vs. Non-Subscribers** — Non-subscribers drove $170,436 in total revenue vs. $62,645 from subscribers, despite similar average spend (~$59–60)
6. **Discount-Dependent Products** — Hat, Sneakers, Coat, Sweater, and Pants had the highest discount usage rates (47–50%)
7. **Customer Segmentation** — Classified customers into New (83), Returning (701), and Loyal (3,116) segments based on purchase history
8. **Top 3 Products per Category** — Identified leading products within Accessories, Clothing, Footwear, and Outerwear
9. **Repeat Buyers & Subscriptions** — Tested whether customers with 5+ purchases are more likely to subscribe (958 subscribed vs. 2,518 non-subscribers among repeat buyers)
10. **Revenue by Age Group** — Young Adults contributed the most revenue ($62,143), followed by Middle-aged, Adult, and Senior segments

### 3. Dashboard (Power BI)
An interactive **Customer Behavior Dashboard** was built to visualize:
- Total customers, average purchase amount, and average review rating (KPIs)
- % of customers by subscription status
- Revenue and sales by product category
- Revenue and sales by age group
- Filters for gender, category, shipping type, and subscription status

## Key Insights

- **Male customers outspend female customers** by roughly 2x in total revenue, despite the dataset's demographic mix
- **Non-subscribers generate significantly more total revenue** than subscribers — subscription status does not strongly correlate with higher average spend
- **Young Adults are the highest-revenue age group**, followed closely by Middle-aged, Adult, and Senior customers
- A meaningful share of customers (839) use discounts while still spending above average, suggesting discounts aren't purely driving down-market behavior
- The **Loyal segment (3,116 customers)** dominates the customer base, indicating strong repeat engagement

## Business Recommendations

- **Boost Subscriptions** — Promote exclusive benefits to convert high-value non-subscribers
- **Customer Loyalty Programs** — Reward repeat buyers to move more customers into the "Loyal" segment
- **Review Discount Policy** — Balance sales boosts against margin control, especially for discount-dependent products
- **Product Positioning** — Highlight top-rated and best-selling products (e.g., Gloves, Sandals, Boots) in campaigns
- **Targeted Marketing** — Focus efforts on high-revenue age groups (Young Adults) and Express-shipping users


## Author

**Raghu**
Data Analyst | Hyderabad, India

---
*This project was built as part of a portfolio demonstrating end-to-end data analysis skills — from raw data cleaning through SQL-based business analysis to interactive dashboard reporting.*
