# 🛍️ Customer Shopping Behavior Analysis

A end-to-end data analytics project that explores customer purchasing patterns, segments shoppers, and surfaces actionable business insights using Python, PostgreSQL, Power BI, and Gamma.

---

## 📌 Overview

This project analyzes transactional data from **3,900 customer purchases** across multiple product categories. The goal is to uncover insights into spending habits, customer loyalty, product preferences, discount dependency, and subscription behavior — all to support smarter, data-driven business decisions.

---

## 📂 Dataset

| Property | Details |
|---|---|
| **Rows** | 3,900 |
| **Columns** | 18 |
| **Source** | Retail transactional dataset |
| **Missing Data** | 37 values in `Review Rating` column (imputed using category median) |

**Key features include:**
- Customer demographics — Age, Gender, Location, Subscription Status
- Purchase details — Item, Category, Purchase Amount, Season, Size, Color
- Shopping behavior — Discount Applied, Previous Purchases, Frequency, Review Rating, Shipping Type

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** (pandas) | Data loading, cleaning, EDA, feature engineering |
| **PostgreSQL** | Structured business queries and analysis |
| **Power BI** | Interactive dashboard and data visualization |
| **Gamma** | Presentation deck |

---

## 🔢 Project Steps

### 1. 🐍 Data Loading & Exploration (Python)
- Imported dataset using `pandas`
- Used `df.info()` and `.describe()` to understand structure and summary statistics
- Identified 37 missing values in the `Review Rating` column

### 2. 🧹 Data Cleaning
- Imputed missing `Review Rating` values using the **median rating per product category**
- Renamed all columns to `snake_case` for consistency
- Verified that `discount_applied` and `promo_code_used` were redundant — dropped `promo_code_used`

### 3. ⚙️ Feature Engineering
- Created `age_group` by binning customer ages into meaningful segments
- Derived `purchase_frequency_days` from purchase frequency data

### 4. 🗄️ Database Integration
- Connected Python to **PostgreSQL** using SQLAlchemy
- Loaded the cleaned DataFrame into a PostgreSQL table for SQL analysis

### 5. 🔍 SQL Analysis (PostgreSQL)
Ran 10 structured queries to answer key business questions:

| # | Query | Key Finding |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 / Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts but spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Shipping Type Comparison | Express avg: $60.48 vs Standard avg: $58.46 |
| 5 | Subscribers vs. Non-Subscribers | Similar avg spend (~$59); non-subscribers drive higher total revenue |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) |
| 7 | Customer Segmentation | Loyal: 3,116 / Returning: 701 / New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | Most repeat buyers (2,518) are non-subscribers |
| 10 | Revenue by Age Group | Young Adults lead at $62,143, followed by Middle-aged at $59,197 |

### 6. 📊 Power BI Dashboard
Built an interactive dashboard featuring:
- KPI cards — Total Customers, Average Purchase Amount, Average Review Rating
- Revenue and Sales breakdown by Category and Age Group
- Subscription status distribution (Yes 27% / No 73%)
- Slicers for Gender, Category, Subscription Status, and Shipping Type

### 7. 📝 Report & Presentation
- Compiled findings into a structured analytical report
- Built a presentation deck using **Gamma** to communicate insights to stakeholders

---

## 📈 Key Results

- **Male customers** generated more than double the revenue of female customers
- **Young Adults** are the highest-revenue age group
- **80%** of the customer base is classified as Loyal
- Only **27%** of customers are subscribers, yet their average spend is comparable to non-subscribers — indicating untapped upsell potential
- **Express shipping** users spend slightly more on average, suggesting a higher-value customer profile
- Products like **Hat, Sneakers, and Coat** are highly discount-dependent, warranting a pricing strategy review

---

## 💡 Business Recommendations

- **Boost Subscriptions** — Promote exclusive perks to convert the 73% non-subscriber base
- **Loyalty Programs** — Reward returning buyers to accelerate their move into the Loyal segment
- **Review Discount Policy** — Reassess heavy discounting on items like Hat and Sneakers to protect margins
- **Product Campaigns** — Feature top-rated products (Gloves, Sandals, Boots) prominently in marketing
- **Targeted Marketing** — Prioritize Young Adults and Express-shipping users who show higher revenue potential

---

## 📁 Project Structure

```
customer-shopping-behavior/
│
├── data/
│   └── customer_shopping_behavior.csv
│
├── notebooks/
│   └── customer_shopping_behaviour_analysis.ipynb
│
├── sql/
│   ├── customer_shopping_behaviour_queries
│
├── dashboard/
│   └── Customer_Behavior_Dashboard.pbix
│
├── report/
│   └── Customer_Shopping_Behavior_Analysis.pdf
│
└── README.md
