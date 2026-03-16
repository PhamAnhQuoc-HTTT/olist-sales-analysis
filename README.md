# 🛒 Olist E-Commerce Sales Analysis Dashboard

End-to-end data analysis project on Brazilian e-commerce platform Olist,
covering 100,000+ orders from 2016–2018.

## 📊 Dashboard Preview

## 🎯 Business Questions Answered
- How has revenue trended over time? Are there seasonal patterns?
- Which product categories drive the most revenue?
- Who are our most valuable customers? (RFM Segmentation)
- How does late delivery impact customer satisfaction?

## 💡 Key Insights
- **7.6% late delivery rate** causes review score to drop from **4.29 → 2.46 out of 5**
  — a 1.83-point impact, the single biggest driver of low ratings
- **24.1% of customers are "At Risk"** of churning — the largest segment,
  suggesting an urgent need for a win-back campaign
- **100% of customers purchased only once** (frequency std = 0) —
  indicating a critical gap in retention and loyalty strategy
- Estimated delivery averages **23 days** vs actual **10 days** —
  Olist deliberately over-estimates to manage customer expectations
- High-value customers exist (max order: **13,664 BRL**) but remain
  underleveraged — upsell and VIP programs could unlock significant revenue

## 🧹 Data Cleaning
- Handled missing values across 7 tables (full details in notebook)
- `order_approved_at`: 160 nulls filled with purchase timestamp
- Product info: 610 nulls filled with `unknown` / median for deleted listings
- Review comments: 88.3% had no title, 58.7% had no message — filled with placeholder
- Resolved **551 duplicate reviews** by keeping most recent submission
- Remaining 4,748 nulls in delivery dates are valid (incomplete/cancelled orders)
- **Final clean dataset: 99,441 orders · 98,673 reviews · 0 unintended duplicates**

## 🛠️ Tech Stack
| Tool | Usage |
|------|-------|
| Python (Pandas, Seaborn, Matplotlib) | Data cleaning, EDA, RFM analysis |
| Google Colab | Development environment |
| Power BI Desktop | Interactive dashboard |
| GitHub | Version control |

## 📁 Dataset
[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
— 9 tables, 100k+ orders, publicly available on Kaggle

## 📂 Project Structure
```
├── data/               # Processed CSV files for Power BI
├── notebooks/          # Python analysis notebook
├── dashboard/          # Power BI .pbix file
└── images/             # Dashboard screenshots
```

## 🔍 Analysis Breakdown

### 1. Data Cleaning & Preprocessing
- Inspected 7 tables for missing values and duplicates
- Applied targeted imputation strategies per column type
- Converted all datetime columns and engineered time features

### 2. Exploratory Data Analysis
- Revenue trend by month (2016–2018)
- Top 10 product categories by revenue
- Order status & review score distribution

### 3. RFM Customer Segmentation
Segmented **96,478 customers** into 6 groups:

| Segment | Count | % |
|---------|-------|---|
| At Risk | 23,266 | 24.1% |
| Loyal Customers | 19,243 | 19.9% |
| New Customers | 15,578 | 16.1% |
| Champions | 15,378 | 15.9% |
| Lost | 15,316 | 15.9% |
| Potential | 7,697 | 8.0% |

### 4. Delivery Performance Analysis
- On-time rate: **92.4%** · Late rate: **7.6%**
- Median actual delivery: **10 days** vs estimated **23 days**
- Late delivery reduces review score by **1.83 points** on average