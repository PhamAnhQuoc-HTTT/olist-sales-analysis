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
  (a 1.83-point impact — the single biggest driver of low ratings)
- **24.1% of customers are "At Risk"** of churning — the largest segment,
  suggesting the need for a win-back campaign
- **100% of customers purchased only once** — indicating a critical gap
  in retention/loyalty strategy
- Estimated delivery time averages **23 days** vs actual **10 days** —
  Olist over-promises, which may be intentional to manage expectations

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
## 🧹 Data Cleaning
- Handled missing values across 7 tables (details in notebook)
- Key decisions: delivery date nulls retained (valid incomplete orders),
  product info filled with median/unknown for deleted listings,
  review comments filled with placeholder for non-text reviews
- Resolved 551 duplicate reviews by keeping most recent submission
- Final dataset: 99,441 orders · 98,673 reviews · 0 unintended duplicates

## 🔍 Analysis Breakdown
### 1. Exploratory Data Analysis
- Revenue trend by month (2016–2018)
- Top 10 product categories by revenue
- Order status & review score distribution

### 2. RFM Customer Segmentation
Segmented 96,478 customers into 6 groups based on
Recency, Frequency, and Monetary value:
- Champions (15.9%), Loyal (19.9%), New (16.1%)
- At Risk (24.1%), Lost (15.9%), Potential (8%)

### 3. Delivery Performance Analysis
- On-time vs late delivery rate
- Correlation between delivery delay and review score
- Delivery time distribution
