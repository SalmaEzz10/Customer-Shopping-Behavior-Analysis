# Customer Shopping Behavior Dashboard

An end-to-end data analysis project exploring customer shopping behavior — from raw CSV to a cleaned SQL database to an interactive Power BI dashboard.

## 🛠️ Tools
- **Python (pandas)** — data cleaning & feature engineering
- **SQL Server** — data storage & analysis queries
- **Power BI** — dashboard & visualization

## 📊 Dataset
Customer-level shopping data with **3,900 rows** covering:

| Column | Description |
|---|---|
| Customer ID, Age, Gender | Customer demographics |
| Item Purchased, Category, Color, Size | Product details |
| Purchase Amount (USD), Season, Location | Transaction details |
| Review Rating, Subscription Status | Customer engagement |
| Shipping Type, Discount Applied, Promo Code Used | Purchase conditions |
| Previous Purchases, Payment Method, Frequency of Purchases | Purchase history |

## 🧹 Data Cleaning (Python)
- Checked for duplicates and missing values
- Filled missing `Review Rating` values with the **median rating per category**
- Standardized column names (lowercase, underscores)
- Created an `age_group` feature (Young Adult / Adult / Middle-aged / Senior) using quartile binning
- Converted `frequency_of_purchases` into a numeric `purchase_frequency_days` field
- Dropped `promo_code_used` (identical to `discount_applied`, so redundant)
- Loaded the cleaned data into **SQL Server** via SQLAlchemy

## 🔎 SQL Analysis
Business questions answered with SQL, including:
- Revenue by gender and by age group
- Customers who used a discount but still spent above average
- Top 5 products by average review rating and by discount rate
- Standard vs. Express shipping — average spend comparison
- Subscriber vs. non-subscriber spending behavior
- Customer segmentation (New / Returning / Loyal) by purchase history
- Top 3 products per category
- Repeat buyers' likelihood to subscribe

## 📈 Dashboard

<img width="1587" height="758" alt="Screenshot 2026-09-18 095401" src="https://github.com/user-attachments/assets/22240a7d-fafc-4d5b-bbcf-390807250555" />

<img width="1245" height="657" alt="Screenshot 2026-09-18 095510" src="https://github.com/user-attachments/assets/deb36553-fe65-442b-8347-3c0602350631" />


### Key Insights
- Total revenue: **233K** across **3.9K customers**, with an average purchase of **$59.76**
- Male customers generate roughly **2x** the revenue of female customers
- **79.9%** of customers are "Loyal," while only **2.13%** are "New" 
- Revenue is highest among **Young Adults** (62K) and **Middle-aged** (59K) customers
- Subscription status has almost no effect on average spend ($59.87 vs. $59.49)
- **Clothing** has the highest number of customers, followed by **Accessories**

## 📁 Project Structure
```
├── customer_shopping_behavior.csv      # Raw dataset
├── Customer_Shopping_Behavior_Analysis.ipynb   # Python cleaning notebook
├── analysis.sql                        # SQL analysis queries
├── dashboard.pbix                      # Power BI dashboard
└── images/                             # Dashboard screenshots
```
