# Global FMCG SALES & PROFITABILITY ANALYTICS DASHBOARD (2023–2025)

Dashboard:

![Image](https://github.com/quafiya-rahim/Global-FMCG-Sales-and-Profitabilty-Analytics-Dashboard-2023-2025-/blob/main/Overview.png)
![Image](https://github.com/quafiya-rahim/Global-FMCG-Sales-and-Profitabilty-Analytics-Dashboard-2023-2025-/blob/main/Profitability%20%26%20Discount%20Analysis.png)
![Image](https://github.com/quafiya-rahim/Global-FMCG-Sales-and-Profitabilty-Analytics-Dashboard-2023-2025-/blob/main/Marketing%20%26%20Promotion%20Performance.png)
![Image](https://github.com/quafiya-rahim/Global-FMCG-Sales-and-Profitabilty-Analytics-Dashboard-2023-2025-/blob/main/Customer%20%26%20Sales%20Rep%20Performance.png)

## 1. Data Overview

This project is an end-to-end analysis of a simulated FMCG commercial dataset covering sales transactions from 2023 to 2025. The analysis includes data cleaning, exploratory data analysis, and an interactive Power BI dashboard to understand business performance across areas such as sales, profitability, discounts, marketing spend, customer segments, products, and regions.The dataset used for analysis contains several columns as stated below:

The dataset contains 18,240 records and 27 columns.

* Order ID – Unique order number. 
* Order Date – Date on which the order was placed.
* Year – Year in which the transaction took place.
* Quarter – Quarter of the year in which the order was placed, such as Q1, Q2, Q3, or Q4.
* Month – Numerical month value of the order date.
* Month Name – Name of the month .
* Region – Broad geographical region where the sale took place, such as Asia, Europe, North America, South America, or Oceania.
* Country – Country associated with the sales transaction.
* City – City where the customer or transaction is located.
* Sales Person – Name of the sales representative responsible for the order.
* Customer Type – Identifies whether the customer belongs to the B2B or B2C segment.
* Sales Channel – Channel through which the product was sold, such as online, distributor, or modern trade.
* Promotion Type – Type of promotional campaign or offer applied to the order.
* Product Category – Main category to which the product belongs.
* Brand – Brand under which the product is sold.
* Product Name – Name of the individual product purchased.
* SKU – Unique Stock Keeping Unit used to identify a specific product.
* Units Sold – Number of product units sold in the transaction.
* Unit Price (USD) – Selling price of one unit of the product before discount.
* Discount % – Percentage discount applied to the order.
* Gross Sales (USD) – Total sales value before applying discounts.
* Marketing Spend (USD) – Marketing expenditure associated with the transaction.
* COGS (USD) – Cost of Goods Sold, representing the direct cost of the products sold.
* Logistics Cost (USD) – Cost related to transportation and delivery of the products.
* Net Revenue (USD) – Revenue generated after adjusting gross sales for the applicable discount.
* Profit (USD) – Profit earned from the transaction after considering product, marketing, and logistics-related costs.
* Profit Margin % – Percentage of net revenue retained as profit.


## 2. Data Cleaning & Transformation (Python + Power Query) 

Data cleaning and validation were done in two stages:

Python (Jupyter Notebook):
- Loaded the raw CSV and inspected shape, data types, and summary statistics.
- Checked for missing values, duplicate rows, and confirmed `Order_ID` uniqueness.
- Converted `Order_Date` to proper datetime format.
- Exported a cleaned CSV for downstream use.

Power Query (Power BI):
- Verified column data types on load (dates, numbers, text).
- Checked categorical fields (Region,Product_Category,Sales_Channel,Promotion_Type,Customer_Type) for inconsistent casing or spacing.
- Confirmed no further transformation was needed beyond what Python had already handled.

![Image](https://github.com/quafiya-rahim/Global-FMCG-Sales-and-Profitabilty-Analytics-Dashboard-2023-2025-/blob/main/power_query.png)



# 3. Key Business Questions & Insights :

Total Revenue USD - 14.45M | Total Profit USD - 3.31M | Avg Profit Margin % - 19.87% | Loss Making Order % - 4.30%

1. Is there a seasonal pattern in sales or profit by category?
Both revenue and profit show a **clear upward trend from 2023 to 2025**, with revenue exhibiting more month-to-month volatility while profit grows more smoothly — suggesting margin stability even as topline revenue fluctuates. A sharp spike is visible toward the end of 2025, warranting further investigation into whether this reflects a genuine seasonal (e.g. festive season) effect or a data artifact.

![Image](https://github.com/user-attachments/assets/5a119c3d-ad2a-4e9c-b073-6412111d8520) 


2. Which regions are profitable on paper but bleeding margin due to discounting?
Average profit margin is fairly consistent across most regions — North America and South America (20.4%), Europe (20.3%), Asia (20.0%) — but Oceania stands out with a notably lower average margin of 16.6%, despite still generating meaningful revenue. This gap flags Oceania as the region most worth reviewing for discount discipline and cost structure.

![Image](https://github.com/user-attachments/assets/24699402-e84d-46d9-a83f-fcf4f02d8821)

3. Which product category has the best discount efficiency (revenue generated per % of discount given)?
Beverages generates the highest revenue per unit of discount ($287.05K), ahead of Household ($241.32K), Personal Care ($215.74K), Snacks ($195.47K), and Dairy & Breakfast ($176.51K). This is a notable tension with Q2's finding — Beverages is the most discount-efficient category in terms of raw revenue generation, yet has the weakest marketing ROI and among the lowest margins. This suggests Beverages sales are volume/discount-driven rather than margin-driven, and warrants a distinct commercial strategy from higher-margin categories like Personal Care.

![Image](https://github.com/user-attachments/assets/24699402-e84d-46d9-a83f-fcf4f02d8821)

4. Does higher marketing spend translate into higher profit, or are we overspending on already-strong products?
Marketing ROI varies significantly by category:Personal Care (269.2%) and Dairy & Breakfast (269.1%) deliver the strongest returns — nearly $2.70 profit per $1 spent — while Beverages lags at just 121.3%, despite likely receiving a large share of the marketing budget. This suggests marketing spend on Beverages is far less efficient than on other categories, and reallocating budget toward Personal Care and Dairy & Breakfast could improve overall marketing ROI.

![Image](https://github.com/user-attachments/assets/24699402-e84d-46d9-a83f-fcf4f02d8821)

5. Which promotion types drive volume vs which ones destroy margin?
No Promo periods drive by far the highest sales volume (~1.5M+ units) — nearly 3x any active promotion — while also maintaining a strong ~22% margin, indicating baseline demand is not primarily promotion-driven.Loyalty Cashback** is a standout: low volume, but margin (~22%) nearly matching No Promo, suggesting it targets high-value repeat customers rather than mass discount-seekers. **Festival Campaign and Flash Discount promotions show the highest loss-making order counts (142 and 155 respectively) and the lowest margins (~15%), making them the least profitable promotion types despite their popularity.

![Image](https://github.com/user-attachments/assets/24699402-e84d-46d9-a83f-fcf4f02d8821)

6. Is B2B or B2C more profitable, and does channel strategy align with that?
B2B is significantly more profitable per order: average order value of $1,190.9 vs.$389.7 for B2C, with a higher average margin (23.7% vs 16.0%) despite receiving a deeper average discount (16.1% vs 9.7%). This shows B2B customers generate far more value per transaction even after accounting for larger negotiated discounts — reinforcing that channel strategy should continue prioritizing B2B relationship growth.

![Image](https://github.com/user-attachments/assets/24699402-e84d-46d9-a83f-fcf4f02d8821)

7. Which sales reps are top revenue generators but poor on profit margin?
Across the top 20 sales reps by revenue, no clear "high revenue, low margin" pattern emerged. Top performers like Oliver Kent ($6.66L revenue, 20.44% margin), Charlotte Ellis ($6.08L, 19.73%), and Amelia Rhodes ($6.05L, 20.26%) all maintain healthy margins alongside high revenue. Conversely, reps with lower margins (Ethan Cole 16.51%, Mia Sutton 16.23%) also have comparatively lower revenue — meaning they aren't over-discounting to chase deal size. This is a positive finding: **top-performing reps maintain margin discipline rather than sacrificing profitability for volume.**

![Sales Rep Performance](images/sales_rep_performance.png)


# Overall Conclusion

- Revenue and profit have grown steadily over the 2023–2025 period, with profit tracking more stable than revenue month-to-month.
- B2B is the more profitable channel per order and warrants continued strategic focus.
- Marketing spend efficiency varies sharply by category — Personal Care and Dairy & Breakfast are high-return, while Beverages is comparatively inefficient despite driving strong raw discount-adjusted revenue.
- No Promo and Loyalty Cashback are the strongest performers on margin; Festival Campaign and Flash Discount are the biggest sources of loss-making orders.
- Sales rep performance shows healthy alignment between revenue and margin — no evidence of systemic over-discounting to close deals.
- Oceania is the one region where average margin meaningfully lags the rest of the business.


# Final Recommendations:

✅ Reallocate a portion of Beverages' marketing budget toward Personal Care and Dairy & Breakfast, where ROI is more than double.
✅ Review discounting practices in Festival Campaign and Flash Discount promotions to reduce loss-making order volume.
✅ Investigate Oceania's lower regional margin — likely driven by discount or cost-structure differences versus other regions.
✅ Continue prioritizing B2B account growth given its outsized profitability per order.
✅ Further investigate the late-2025 revenue spike to confirm whether it reflects genuine seasonality worth planning around.



