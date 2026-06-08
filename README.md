# 🛍️ Customer Shopping Behavior Analysis

A data analysis project that explores customer shopping patterns using transactional data. The goal was to understand how customers shop — what they buy, how much they spend, and what factors influence their behavior.

---

## 📌 About the Project

This project analyzes **3,900 customer transactions** across different product categories. We cleaned the data in Python, ran business queries in PostgreSQL, and built a dashboard in Power BI to present the findings visually.

---

## 📂 Dataset Overview

| Feature | Details |
|---|---|
| Total Records | 3,900 rows |
| Total Columns | 18 |
| Missing Data | 37 values in `Review Rating` column |

**Key columns include:**
- Customer info — Age, Gender, Location, Subscription Status
- Purchase details — Item, Category, Amount (USD), Season, Size, Color
- Behavior data — Discount Applied, Previous Purchases, Frequency, Shipping Type, Review Rating

---

## 🔧 What We Did

### 1. Data Cleaning (Python + Pandas)
- Loaded the dataset and explored its structure using `df.info()` and `.describe()`
- Filled missing `Review Rating` values using the **median rating per product category**
- Renamed columns to **snake_case** for consistency
- Created new features:
  - `age_group` — binned customer ages into groups
  - `purchase_frequency_days` — derived from purchase frequency data
- Checked if `discount_applied` and `promo_code_used` were duplicates → dropped `promo_code_used`
- Loaded the cleaned data into a **PostgreSQL database** for SQL analysis

### 2. SQL Analysis (PostgreSQL)
We answered 10 business questions:

1. **Revenue by Gender** — Males generated ~$157K vs Females ~$75K
2. **High-Spending Discount Users** — 839 customers used discounts but still spent above average
3. **Top 5 Products by Rating** — Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)
4. **Shipping Type Comparison** — Express ($60.48 avg) slightly beats Standard ($58.46 avg)
5. **Subscribers vs Non-Subscribers** — Similar avg spend (~$59-60), but non-subscribers make up the majority
6. **Discount-Dependent Products** — Hat, Sneakers, Coat, Sweater, Pants had the most discounted purchases
7. **Customer Segments** — 3,116 Loyal | 701 Returning | 83 New customers
8. **Top 3 Products per Category** — e.g., Accessories: Jewelry, Sunglasses, Belt
9. **Repeat Buyers & Subscriptions** — Customers with 5+ purchases: 2,518 non-subscribed vs 958 subscribed
10. **Revenue by Age Group** — Young Adults led with $62K, followed by Middle-aged at $59K

### 3. Power BI Dashboard
Built an interactive dashboard with filters for subscription status, gender, category, and shipping type. Includes charts for revenue by age group, sales by category, and customer distribution.

---

## 📊 Key Findings

- Male customers contribute **significantly more revenue** than female customers
- The majority of customers (3,116 out of 3,900) fall in the **Loyal** segment
- **Discounts are widely used** but loyal customers still spend a good amount
- **Young Adults** are the highest revenue-generating age group
- Express shipping users tend to spend slightly more

---

## 💡 Business Recommendations

- **Boost subscriptions** — add exclusive perks for subscribers to increase that base
- **Loyalty rewards** — push returning customers into the loyal segment with reward programs
- **Revisit discount strategy** — discounts drive volume but need margin checks
- **Focus on top-rated products** — Gloves, Sandals, Boots should be highlighted in campaigns
- **Target Young Adults** — they generate the most revenue, prioritize marketing toward them

---

## 🛠️ Tech Stack

- **Python** — Pandas for data cleaning and feature engineering
- **PostgreSQL** — SQL queries for business analysis
- **Power BI** — Interactive dashboard for visualization

---

## 📁 Project Structure

```
├── data/
│   └── customer_behavior.csv        # Raw dataset
├── notebooks/
│   └── eda_cleaning.ipynb           # Python EDA and cleaning
├── sql/
│   └── queries.sql                  # All 10 business queries
├── dashboard/
│   └── customer_behavior.pbix       # Power BI dashboard file
└── README.md
```

---

## 🚀 How to Run

1. Clone the repo
2. Install dependencies: `pip install pandas sqlalchemy psycopg2`
3. Run the Jupyter notebook for data cleaning
4. Import the cleaned data into PostgreSQL
5. Execute the SQL queries from the `sql/` folder
6. Open the `.pbix` file in Power BI Desktop

---

*Made as part of a data analysis internship project.*
