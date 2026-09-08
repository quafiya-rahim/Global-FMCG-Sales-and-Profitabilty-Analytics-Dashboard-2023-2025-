###Global FMCG Sales & Profitability Analytics Dashboard (2023–2025)

An end-to-end analytics project on a simulated FMCG commercial dataset covering 18,240 orders across 17 countries, 5 regions, and 5 product categories. The project combines data cleaning, exploratory analysis, and an interactive Power BI dashboard to answer real business questions around profitability, discounting, marketing efficiency, and sales performance.

Tools used: Python (Pandas, NumPy, Matplotlib, Seaborn) and Power Query for data cleaning and validation, Power BI for dashboard building and DAX-based analysis.

1. Data Overview
Rows: 18,240 orders
Date range: 2023-01-01 to 2025-12-31
Regions: 5 | Countries: 17 | Brands: 17 | SKUs: 30
Total Revenue: $14.45M | Total Profit: $3.31M | Average Margin: 19.87%
Key fields: Order date, region/country/city, sales person, customer type (B2B/B2C), sales channel, promotion type, product category/brand/SKU, units sold,
discount %, marketing spend, COGS, logistics cost, net revenue, profit, profit margin % .

2. Data Cleaning (Python + Power Query)

Data cleaning and validation were done in two stages:

Python (Jupyter Notebook):

Loaded the raw CSV and inspected shape, data types, and summary statistics
Checked for missing values, duplicate rows, and confirmed Order_ID uniqueness
Converted Order_Date to proper datetime format
Cross-validated aggregate figures (e.g. total marketing spend) against the Power BI model to catch formatting/calculation mismatches
Exported a cleaned CSV for downstream use

Power Query (Power BI):

Verified column data types on load (dates, numbers, text)
Checked categorical fields (Region, Product_Category, Sales_Channel, Promotion_Type, Customer_Type) for inconsistent casing or spacing
Confirmed no further transformation was needed beyond what Python had already handled

3. Dashboard Pages
Page	Focus
1	Overview — Revenue, Profit & Global Performance
2	Profitability & Discount Analysis
3	Marketing & Promotion Performance
4	Customer & Sales Rep Performance

4. Key Business Questions & Insights
Q1. Which countries/regions are profitable on paper but bleeding margin due to discounting?

Average profit margin is fairly consistent across most regions — North America and South America (20.4%), Europe (20.3%), Asia (20.0%) — but Oceania 
stands out with a notably lower average margin of 16.6%, despite still generating meaningful revenue. This gap flags Oceania as 
the region most worth reviewing for discount discipline and cost structure.

Q2. Does higher marketing spend translate into higher profit, or are we overspending on already-strong products?

Marketing ROI varies significantly by category: Personal Care (269.2%) and Dairy & Breakfast (269.1%) deliver the strongest returns — nearly $2.70 profit per $1 
spent — while Beverages lags at just 121.3%, despite likely receiving a large share of the marketing budget. This suggests marketing spend on Beverages is far less 
efficient than on other categories, and reallocating budget toward Personal Care and Dairy & Breakfast could improve overall marketing ROI.

Q3. Which promotion types drive volume versus which ones destroy margin?

No Promo periods drive by far the highest sales volume (~1.5M+ units) — nearly 3x any active promotion — while also maintaining a strong ~22% margin, indicating
baseline demand is not primarily promotion-driven. Loyalty Cashback is a standout: low volume, but margin (~22%) nearly matching No Promo, suggesting it targets 
high-value repeat customers rather than mass discount-seekers. Festival Campaign and Flash Discount promotions show the highest loss-making order counts 
(142 and 155 respectively) and the lowest margins (~15%), making them the least profitable promotion types despite their popularity.

Q4. Is B2B or B2C more profitable, and does channel strategy align with that?

B2B is significantly more profitable per order: average order value of $1,190.9 vs. $389.7 for B2C, with a higher average margin (23.7% vs 16.0%)
despite receiving a deeper average discount (16.1% vs 9.7%). This shows B2B customers generate far more value per transaction even after accounting for 
larger negotiated discounts — reinforcing that channel strategy should continue prioritizing B2B relationship growth.

Q5. Which sales reps are top revenue generators but poor on profit margin?

Across the top 20 sales reps by revenue, no clear "high revenue, low margin" pattern emerged. Top performers like Oliver Kent ($6.66L revenue, 20.44% margin), 
Charlotte Ellis ($6.08L, 19.73%), and Amelia Rhodes ($6.05L, 20.26%) all maintain healthy margins alongside high revenue. Conversely, reps with lower margins 
(Ethan Cole 16.51%, Mia Sutton 16.23%) also have comparatively lower revenue — meaning they aren't over-discounting to chase deal size. 
This is a positive finding: top-performing reps maintain margin discipline rather than sacrificing profitability for volume.

Q6. Is there a seasonal pattern in sales or profit by category?

Both revenue and profit show a clear upward trend from 2023 to 2025, with revenue exhibiting more month-to-month volatility while profit grows
more smoothly — suggesting margin stability even as topline revenue fluctuates. A sharp spike is visible toward the end of 2025, warranting further
investigation into whether this reflects a genuine seasonal (e.g. festive season) effect or a data artifact.

Q7. Which product category has the best discount efficiency (revenue generated per % of discount given)?

Beverages generates the highest revenue per unit of discount ($287.05K), ahead of Household ($241.32K), Personal Care ($215.74K), Snacks ($195.47K), and
Dairy & Breakfast ($176.51K). This is a notable tension with Q2's finding — Beverages is the most discount-efficient category in terms of raw revenue generation, 
yet has the weakest marketing ROI and among the lowest margins. This suggests Beverages sales are volume/discount-driven rather than margin-driven, and warrants a 
distinct commercial strategy from higher-margin categories like Personal Care.

Overall Conclusion
Revenue and profit have grown steadily over the 2023–2025 period, with profit tracking more stable than revenue month-to-month.
B2B is the more profitable channel per order and warrants continued strategic focus.
Marketing spend efficiency varies sharply by category — Personal Care and Dairy & Breakfast are high-return, while Beverages is comparatively inefficient despite 
driving strong raw discount-adjusted revenue.
No Promo and Loyalty Cashback are the strongest performers on margin; Festival Campaign and Flash Discount are the biggest sources of loss-making orders.
Sales rep performance shows healthy alignment between revenue and margin — no evidence of systemic over-discounting to close deals.

Recommendations
Reallocate a portion of Beverages' marketing budget toward Personal Care and Dairy & Breakfast, where ROI is more than double.
Review discounting practices in Festival Campaign and Flash Discount promotions to reduce loss-making order volume.
Investigate Oceania's lower regional margin — likely driven by discount or cost-structure differences versus other regions.
Continue prioritizing B2B account growth given its outsized profitability per order.
Further investigate the late-2025 revenue spike to confirm whether it reflects genuine seasonality worth planning around.


Oceania is the one region where average margin meaningfully lags the rest of the business.

Verified column data types on load (dates, numbers, text)
Checked categorical fields (Region, Product_Category, Sales_Channel, Promotion_Type, Customer_Type) for inconsistent casing or spacing
Confirmed no further transformation was needed beyond what Python had already handled
