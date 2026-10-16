# Chocolate Sales Analysis (2022–2023)

## Background and Overview

Throughout 2022 and 2023, a chocolate company recorded sales across multiple products, countries, and sales channels. However, overall revenue alone does not reveal which areas drive performance, how sales outcomes vary across discount levels, or when potential sales opportunities emerge.

To help create data-informed decisions, insights and recommendations are provided on the following areas:
- **Sales Trend Analysis**:  Evaluation of historical monthly sales patterns and potential seasonal peaks.
- **Revenue Contribution**: Focused on the products, countries, and sales channels contributing most to recorded revenue.
- **Discount Analysis**: Examination of how order size, revenue contribution, and monthly order counts vary across discount bands.
  
The Kaggle dataset can be found [here](https://www.kaggle.com/datasets/arjunmehta1992/chocolate-sales-in-20222023)  
You can view the interactive Tableau dashboard [here](https://public.tableau.com/views/Chocolate_Sales_Dashboard_17919081098370/ChocolateSalesDashboard)
> **Note:** The workbook is available for download from the dashboard page. Click **Download -> Tableau Workbook**.

<br/>

## Data Structure Overview

The dataset contains order-level chocolate sales records with information about products, markets, sales channels, order dates, discounts, shipment quantities, and marketing spend.

Each record represents an order in the dataset, identified by its order ID.

### Key Data Fields

| Field | Description |
|---|---|
| `Order_ID` | Unique identifier for an order |
| `Product` | Chocolate product associated with the order |
| `Country` | Market where the order was recorded |
| `Channel` | Sales channel: Retail, Online, or Wholesale |
| `Salesperson` | Salesperson associated with the order |
| `Order_Date` | Date the order was recorded |
| `Discount_Pct` | Discount percentage applied to the order |
| `Price_per_Box` | Price per box |
| `Marketing_Spend` | Marketing expenditure recorded in the dataset |
| `Boxes_Shipped` | Number of boxes shipped for the order |
| `Amount` | Recorded order amount used as the revenue metric in this analysis |

### Data Quality Report

The `Amount` field doesn't match the documented formula (`Boxes_Shipped × Price_per_Box`) in **~99.99% of records**, averaging **17.11% lower** than the computed values.

The original `Amount` values were kept as the revenue metric, so findings reflect **recorded amounts, not independently verified revenue**. This discrepancy should be reconciled with the data source before the figures are used for financial or high-stakes decisions.

<br/>

## Executive Summary

The company generated approximately **$102.57 million in revenue** across 2022-2023, with monthly revenue ranging from **$3.5M to $5.7M**.

- **Products:** Sales are concentrated in three products: 70% Dark Bar, Mixed Assortment Box, and Truffle Gift Box, which together account for **63.67% of revenue**. 70% Dark Bar is the largest contributor at **~$26M (25.7%)** and the only product to exceed $150K in marketing spend, while Hazelnut Milk Bar is the smallest at **~$2M (2.11%)**.
- **Seasonality:** Sales peak from November to January and dip steadily from February to August, then rebuild from September as shipment volume rises. Revenue grew year over year by **8.19% in January**, **5.74% in November**, and **3.20% in December**.
- **Markets:** Australia (**41.37%**) and Brazil (**35.71%**) are the largest markets, driving **77.08%** of sales, while India (**6.33%**) and Japan (**5.52%**) are the smallest, contributing **11.85%** combined.
- **Discounts:** The **11-20%** band generates half of revenue (**50.27%**), and deeper discounts are associated with larger orders (**122 to 191** boxes per order). Monthly order counts stay steady in every discount band, so the discount mix does not shift between peak and off-peak months, suggesting room to test shifting deeper discounts toward the February-August dip.
- **Channels:** Retail (**~$53M**) and Wholesale (**~$37M**) lead by a wide margin, while Online (**~$11M**) trails far behind. Retail and Wholesale in Australia and Brazil drive sales, especially in peak season, whereas Online does not respond to seasonal increases in shipment volume, which may indicate room for growth.

<br/>

## Summary of Insights

### Sales Performance
- **Monthly revenue and seasonality:** Monthly revenue ranged from **$3.5M to $5.7M** across 2022-2023. **December** was the peak month at roughly **$5.4M-$5.7M**, while **June** was the weakest at roughly **$3.5M-$3.7M**. This pattern held in both years, with year-over-year growth of **4.38% in June** and **3.20% in December**, suggesting that sales are growing at both the low and peak points of the cycle.

- **Price per box:** Price per box averaged **$5-$7 monthly**, **$4-$9 weekly**, and **$3-$15 daily**, widening as the time granularity gets finer. The top three products (**70% Dark Bar, Mixed Assortment Box, and Truffle Gift Box**) held a stable **$4-$8** range at every granularity, while the other products showed much wider swings. This suggests pricing is more consistent for the best-selling products.

- **Marketing spend:** Monthly marketing spend stayed **below $150K per product**, except for **70% Dark Bar**, the top-selling product, at roughly **$250K per month**. It is the only product above the $150K level, so its spend is worth reviewing with the marketing team.
  
<img width="1433" height="748" alt="image" src="https://github.com/user-attachments/assets/ecf6cdd5-e0e9-45a6-a0f3-8b3b1e9bacc8" />

  
### Product Performance
- **Revenue concentration:** Sales are concentrated in three products: **70% Dark Bar, Mixed Assortment Box, and Truffle Gift Box**, which together generated **~$65M (63.67%)** of total revenue. This dependence on a few products is a concentration risk. It also leaves room to test new strategies on lower-revenue products or to introduce products in lower-performing countries.

- **Revenue vs. marketing spend:** **70% Dark Bar** is the top-selling product at **$26.3M** in revenue, and it also has the highest marketing spend at **~$6.1M** across 2022-2023. **Mixed Assortment Box** follows with **$19.4M** in revenue on only **$2M** in spend, and **Truffle Gift Box** generated **$19.4M** on **$3M**.

<img width="1231" height="756" alt="image" src="https://github.com/user-attachments/assets/405475f0-1b07-4964-82ae-c96b5e6560e9" />


### Country and Marketing Channel Performance
- **Country contribution:** Revenue is concentrated in two markets. **Australia** is the largest at **41.37% (~$42.4M)**, followed by **Brazil** at **35.71% (~$36.6M)**. Together they account for **77.08% (~$79.1M)** of revenue.

- **Sales channel contribution:** **Retail** is the largest channel at **52.44% (~$53.8M)**, followed by **Wholesale** at **36.55% (~$37.5M)** and **Online** at **11.01% (~$11.3M)**. Online trails the other two channels by a wide margin.

- **Seasonality by channel:** Retail and Wholesale rise during peak season, while Online stays relatively flat throughout the year.

<img width="1441" height="767" alt="image" src="https://github.com/user-attachments/assets/91155c8f-5b9e-4a16-8677-8b7c9b998425" />


### Discount Performance
Discount bands were created in 10-point increments: **0-10%, 11-20%, 21-30%, and 30%+**.

- **Order size:** Average boxes per order rise with each discount band (**122, 146, 176, and 191**), indicating that deeper discounts are associated with larger orders.

- **Revenue contribution:** The **11-20%** band generates half of total revenue (**50.27%**), followed by **0-10%** band (**33.18%**) and **21-30%** band (**15.71%**). The **30%+** band contributes less than 1% (**0.83%**) of revenue.

- **Seasonality:** Monthly order counts stay steady within every discount band throughout 2022-2023, so the mix of discount bands does not change between peak and off-peak months. This describes how discounts were used, not whether seasonal discounting would improve results.
  
<img width="1432" height="767" alt="image" src="https://github.com/user-attachments/assets/4c0b9439-7a28-4f95-9ae7-4cd45b2c45ad" />


<br/>
<br/>

## Recommendations

Based on the findings and insights from this analysis, the following recommendations outline potential opportunities for improving marketing strategies and prioritizing investments:

| Priority | Recommendation | Supporting Insight | Suggested Action | Related Team |
|---|---|---|---|---|
| **High** | **Review 70% Dark Bar's marketing spend** | Top product (**~$26M, 25.7%**) and the only one above **$150K** in monthly marketing spend (roughly **$250K**). Mixed Assortment Box and Truffle Gift Box generate substantial revenue on lower spend. | Review the allocation with the marketing team to confirm whether the higher spend is intentional and what it returns. | Marketing |
| **High** | **Pilot shifting deeper discounts toward the February-August dip** | Monthly order counts stay steady within every discount band, so the discount mix does not change between peak and off-peak months. Deeper discounts are not targeted at the months that need support. | Concentrate deeper discounts in February-August and ease them in November-January, then monitor order size and revenue to see whether the effect holds. | Sales, Marketing |
| **Medium** | **Test a small Online marketing push for the top three products** | Online is the smallest channel (**11.01%**) and stays flat during peak season, while Retail and Wholesale rise. | Run a limited test on 70% Dark Bar, Mixed Assortment Box, and Truffle Gift Box within Online, and compare Online revenue before and after the added effort. | Marketing, Sales |
| **Low** | **Test price stabilization on the lowest-revenue products first** | The top three products hold a stable **$4-$8** price-per-box range across time granularities, while other products fluctuate more. | Start with a small pilot on the bottom products (Hazelnut Milk Bar, Salted Caramel Bar, and 85% Dark Bar), where a mistake has the lowest revenue impact. | Marketing, Finance |
 
<br/>

## Limitations and Caveats

- **Inconsistent `Amount` values:** The `Amount` field does not match the documented formula (`Boxes_Shipped × Price_per_Box`) in about **99.99%** of records, averaging **17.11% lower**. This could not be reconciled with the engineering team or data owner, so all revenue figures reflect recorded amounts and not independently verified revenue.
- **No cost or profit data:** The dataset has no cost, margin, or customer acquisition cost (CAC) data. Findings describe revenue and volume only, and cannot establish profitability, marketing ROI, or the best discount level. Marketing spend is also recorded by product, not by channel or country.

