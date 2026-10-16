📊 Amazon Product Sales & Profit Analysis – Power BI Dashboard

An interactive Power BI dashboard that analyzes Amazon product data across sales performance and profitability. It tracks year-to-date and quarter-to-date metrics, monthly and weekly trends, category performance and profit margins, and ends with a page of written business insights.

📌 Project Overview

The report helps answer questions such as:

How much revenue has been generated year-to-date and quarter-to-date?
Which months and weeks drive the most sales?
Which product categories lead in sales, profit and customer reviews?
What are the total cost, profit and profit margin?
How does the sales and profit trend change over time?
🗂️ Dashboard Pages
1. Sales Analysis
Visual	Description
KPI cards	YTD Sales, YTD Products Sold, Total Shipments, QTD Sales, YTD Reviews
Sales by Month	Area chart of monthly sales
Sales by Week	Column chart of weekly sales
Top 5 Products by Sales	Bar chart by product category
Top 5 Products by Reviews	Bar chart by product category
Sales by Product Category	Table with YTD sales, QTD sales and % share of total
Slicers	Month, Product Category, Shipment, Product Description
2. Profit Analysis
Visual	Description
KPI cards	Total Sales, Total Profit, Total Cost, Total Quantity Sold, Average Product Price
Profit by Product Category	Bar chart
Sales & Profit Trend	Area chart by month
Top 5 Products by Profit	Donut chart
Profit Margin	Gauge (profit vs. total sales)
Slicers	Product Category, Month, Shipment, Product Description
3. Insights

A summary page with written takeaways for both sales and profit (see below).

🔑 Key Insights

Sales

YTD sales reached $8.4M, indicating strong overall performance.
December was the peak month at $1.35M, followed by September at $1.25M; February was the lowest at $0.22M.
Camera was the top-selling category at $2.48M, followed by Men Shoes at $2.24M.
Sales were notably stronger from September to December.

Profit

Total profit reached $5.05M against total sales of about $8M, with a total cost of $3.37M.
Camera also generated the highest profit at $1.49M, followed by Men Shoes at $1.34M.
About 89K products were sold at an average price of $94.53.
Camera is the strongest contributor to both sales and profit.
🧮 Data Model

Source: Amazon_Combined_Data.xlsx (imported via Power Query)

Table	Purpose	Key Columns
Amazon_Data Sales	Sales analysis	Product Category, Product Description, Price(Dollar), Number of reviews, Shipment, Order Date, YTD Sales
Amazon_Data profit	Profit analysis	Product Category, Product Description, Price(Dollar), Number of reviews, Shipment, Order Date, Quantity, Total Sales, Cost Price, Total Cost, Profit
Date table	Time intelligence	Date, Months, Month number, week
DAX Measures
DAX
YTD Product sold = TOTALYTD(COUNT('Amazon_Data Sales'[Product Category]), 'Date table'[Date])

QTD Sales = TOTALQTD(SUM('Amazon_Data Sales'[Price(Dollar)]), 'Date table'[Date])

YTD Reviews = TOTALYTD(SUM('Amazon_Data Sales'[Number of  reviews]), 'Date table'[Date])

Average Customer Rating = AVERAGE('Amazon_Data profit'[Number of  reviews])

Profit Margin % =
DIVIDE(
    SUM('Amazon_Data profit'[Profit]),
    SUM('Amazon_Data Sales'[YTD Sales]),
    0
)
🛠️ Tools & Skills Demonstrated
Power BI Desktop – report design, custom layout, themes and image assets
Power Query – importing and shaping data from Excel
DAX – time-intelligence measures (YTD, QTD) and ratio calculations
Data modelling – separate sales and profit tables with a dedicated date table
Visualization – KPI cards, area/column/bar/donut charts, gauge, tables and slicers
Data storytelling – a dedicated insights page
🚀 How to Use
Clone or download this repository.
bash
   git clone https://github.com/<your-username>/<your-repo-name>.g
