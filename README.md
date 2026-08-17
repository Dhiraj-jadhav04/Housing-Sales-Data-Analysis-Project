# Housing-Sales-Data-Analysis-Project

🏠 Housing Sales Analytics | BigQuery + SQL + Power BI

📊 Project Overview

An end-to-end Housing Sales Analytics & Business Intelligence project designed to transform raw housing transaction data into actionable insights for sales, pricing, regional performance, and property segmentation.

The project uses Google BigQuery, SQL, Power Query, DAX, Power BI, and Power BI Service to build an interactive analytics solution that helps identify sales growth and decline, high-performing regions, pricing patterns, and opportunities for business improvement.

The final solution follows the pipeline:

CSV → Google BigQuery → SQL → Power BI → Power Query → DAX → Interactive Dashboards → Power BI Service → Scheduled Refresh

---

🎯 Business Problem

Housing transaction data contains valuable information such as purchase price, sales type, region, house type, SQM, SQM price, construction year, inflation, interest rate, and yield.

However, raw transaction data does not directly answer important business questions:

- Which sales channels are growing or declining?
- Which regions generate the highest sales?
- Which regions have increasing or decreasing property prices?
- How do offer prices compare with purchase prices?
- Which house types have the highest transaction values?
- How does price per SQM vary across regions and property types?
- Which property characteristics are associated with purchase price?
- Where should management focus its sales and pricing strategy?

The objective was therefore to create a single interactive reporting layer that enables decision-makers to identify growth drivers, declining segments, regional opportunities, and pricing patterns.

---

🛠️ Tech Stack

Technology| Purpose
Google BigQuery| Cloud data storage and SQL analysis
SQL| Data exploration, aggregation and validation
Power Query| Data cleaning and transformation
DAX| KPI and business metric development
Power BI Desktop| Dashboard development and visualization
Power BI Service| Report publishing and scheduled refresh
CSV| Source dataset

---

🔄 Data & Analytics Workflow

                Housing CSV Dataset
                       │
                       ▼
                Google BigQuery
                       │
                       ▼
                  SQL Analysis
                       │
                       ▼
                Power BI Desktop
                       │
                       ▼
             Power Query Cleaning
                       │
                       ▼
                  DAX Modeling
                       │
                       ▼
              Interactive Dashboards
                       │
             ┌─────────┼─────────┐
             ▼         ▼         ▼
        Market      Sales      House Type
        Overview   Performance   Analysis
             │         │         │
             └─────────┼─────────┘
                       ▼
                 Power BI Service
                       │
                       ▼
                Scheduled Refresh

The project follows a descriptive and diagnostic analytics approach: identifying what happened, where performance differs, and which segments require business attention.

---

🧹 Data Preparation

Google BigQuery

The raw housing CSV data was loaded into BigQuery for cloud-based analysis.

SQL was used for:

- Data exploration
- Record inspection
- Sales-type analysis
- Average purchase price analysis
- Test table creation
- Data validation and updates

Power Query

Power Query was then used in Power BI to:

- Handle missing/null values
- Clean relevant fields
- Prepare the dataset for analysis
- Create a reliable reporting layer

---

📐 Key KPIs & DAX Analysis

The project includes several business-focused KPIs.

1. YOY Sales Growth

Measures year-over-year change in purchase sales and compares performance across sales types.

2. Rolling 12-Month Sales

Measures sales value over the latest 12-month period.

Dashboard result: ≈ 13bn

3. Units Sold – Latest Year & Quarter

Measures distinct properties sold during the latest year/quarter.

Dashboard result: 77 units

4. Total YTD Sales

Tracks cumulative sales from the beginning of the year.

5. Median Sales Price Change

Compares current-year and previous-year median purchase prices by region.

6. Average Price per SQM

Compares property pricing on a square-meter basis across regions.

7. Offer Price

The dataset did not directly contain an offer-price field, so an offer-price measure was derived using purchase price and the available offer-to-purchase percentage change.

8. Offer-to-SQM Ratio

Compares offer value against property area across sales types.

9. Property Age

Property age was derived using transaction year and construction year.

These KPIs provide the core framework for the dashboards.

---

📊 Power BI Dashboards

1️⃣ House Market Overview

The first dashboard provides an executive-level overview of:

- YOY Sales Growth by Sales Type
- Median Sales Price Change by Region
- Units Sold
- Rolling 12-Month Sales
- Offer Price vs Purchase Price

Key Findings

Metric| Result
Auction Sales YOY| +29%
Regular Sales YOY| -21%
Other Sales YOY| -21%
Family Sales YOY| -75%
Jutland Median Price Change| +5.3%
Bornholm Median Price Change| -5.0%
Rolling 12-Month Sales| ≈13bn
Latest Year/Quarter Units| 77

Auction was the only sales channel showing positive YOY growth, while family sales recorded the largest decline.

---

2️⃣ Sales Performance Dashboard

This dashboard focuses on:

- Sales by Region
- Key Influencers
- YTD Sales
- Offer-to-SQM Ratio
- Average Price SQM by Region

Regional Sales

Region| Reported Sales
🇩🇰 Zealand| 95bn
🇩🇰 Jutland| 81bn
Fyn & Islands| 15bn
Bornholm| 1bn

Regional Pricing

Zealand recorded the highest average SQM price at approximately 20.85K, followed by Fyn & Islands at 13.62K.

This highlights the importance of using different pricing and sales strategies across regions.

---

3️⃣ House Type Analysis

The third dashboard analyzes property-level segmentation.

Average Purchase Price

House Type| Avg. Purchase Price
Farm| 2.7M
Apartment| 2.4M
Townhouse| 2.1M
Villa| 1.8M
Summerhouse| 1.2M

Offer-to-SQM Ratio

Sales Type| Offer-to-SQM
Regular Sale| 15K
Other Sale| 14K
Family Sale| 12K
Auction| 11K

The dashboard also compares inflation, interest and yield across house types to provide additional market context.

---

🔍 Key Business Insights

🚀 1. Auction Sales Are Growing

Auction sales recorded approximately:

+29% YoY growth

This was the only sales type showing positive growth in the dashboard.

Business implication: Investigate the regions, cities, house types and price bands driving auction growth and identify whether successful characteristics can be scaled.

---

⚠️ 2. Family Sales Require Immediate Attention

Family sales declined by:

-75% YoY

This represents the largest decline among the analyzed sales channels.

Recommended investigation:

- Pricing
- Inventory mix
- Geography
- Property age
- Customer demand

---

📉 3. Regular & Other Sales Declined

Both regular sales and other sales declined by:

-21% YoY

This indicates that growth is not uniform across the business and that traditional sales channels require corrective analysis.

---

📈 4. Jutland Shows Strongest Price Growth

Jutland recorded:

+5.3% median sales price change

This was the strongest regional price movement in the dashboard.

---

📉 5. Bornholm Shows Negative Price Movement

Bornholm recorded:

-5.0% median sales price change

Combined with approximately 1bn in reported sales, this region should receive additional investigation before increasing inventory.

---

🏙️ 6. Sales Are Concentrated in Zealand & Jutland

Reported regional sales:

Zealand: 95bn

Jutland: 81bn

These two regions represent the largest reported sales values in the dashboard.

---

💡 Proposed Business Solutions

1. Scale the Auction Growth Engine

Since auction sales increased 29% YoY, identify the specific:

- Regions
- Cities
- House types
- Price bands

driving this growth.

Then test whether similar characteristics can be expanded.

2. Recover Declining Sales Channels

Develop a root-cause analysis for:

- Regular sales: -21%
- Other sales: -21%
- Family sales: -75%

Focus on pricing, inventory mix, geography, property age and demand.

3. Protect High-Value Markets

Use different strategies for:

- Zealand → high sales-volume strategy
- Jutland → price-growth strategy

4. Investigate Weak Regions

Bornholm's -5.0% median price movement and approximately 1bn sales suggest the need to evaluate:

- Local demand
- Property mix
- Pricing
- Inventory

before expanding supply.

5. Implement Data-Driven Pricing

Combine:

Offer Price
      +
Purchase Price
      +
SQM
      +
SQM Price
      +
Region
      +
House Type

to establish pricing benchmarks.

6. Segment Property Inventory

Use different strategies for different property segments:

- Farms / Apartments → premium-value strategy
- Townhouses / Villas → mid-market strategy
- Summerhouses → volume / affordability strategy

7. Operationalize BI Reporting

Use Power BI Service with scheduled refresh and establish recurring reviews of:

- YOY growth
- Rolling 12-month sales
- Regional price change
- Sales-channel performance

The proposed business solutions and management cadence are documented in the final report.

---

📌 Important Note on Profitability

This project analyzes sales, transaction values and pricing, but the dataset does not contain reliable cost, expense, acquisition-cost or margin information.

Therefore:

«+29% represents sales growth, not +29% profit.»

Similarly, the -21% and -75% figures represent sales declines, not profit losses.

A future version can introduce:

- Property acquisition cost
- Selling expenses
- Commission
- Marketing cost
- Gross margin
- Net profit

to calculate actual profitability.

---

🎯 Business Impact

The project transforms raw housing transactions into a decision-support system that helps management:

✅ Identify growing and declining sales channels
✅ Compare regional sales performance
✅ Monitor pricing movements
✅ Identify high-value property segments
✅ Compare offer and purchase prices
✅ Analyze price per SQM
✅ Monitor recent sales activity
✅ Support data-driven pricing decisions
✅ Identify regions requiring investigation
✅ Perform interactive self-service analysis
✅ Automate reporting through Power BI Service

---

🚀 Future Enhancements

The current solution can be extended by adding:

Profitability Analytics

- Gross Profit
- Net Profit
- Profit Margin
- Revenue vs Cost

Customer Analytics

- Customer segmentation
- Buyer profiles
- Repeat customers
- Customer lifetime value

Sales Funnel

- Property listings
- Offers received
- Negotiations
- Completed purchases
- Conversion rate

Inventory Analytics

- Available properties
- Inventory aging
- Days on market
- Unsold inventory

Predictive Analytics

- Sales forecasting
- Price prediction
- Demand forecasting
- Regional growth prediction

The final report specifically identifies profit/margin data, customer segmentation, inventory availability, conversion rates and forecasting as potential future extensions.

---

📁 Suggested Repository Structure

Housing-Sales-Analytics/
│
├── README.md
│
├── data/
│   └── Housing_Data.csv
│
├── sql/
│   └── housing_analysis.sql
│
├── powerbi/
│   └── Housing_Sales_Analytics.pbix
│
├── dashboard/
│   ├── house_market_overview.png
│   ├── sales_performance.png
│   └── house_type_analysis.png
│
├── report/
│   └── Housing_Sales_Analytics_Business_Report.pdf
│
└── docs/
    └── project_documentation.md

---

💼 Resume Project Description

Housing Sales Analytics | Google BigQuery, SQL, Power BI, DAX

- Built an end-to-end BigQuery–Power BI sales analytics solution for housing transaction data, covering regional performance, sales channels, pricing and property segmentation.
- Developed DAX KPIs for YOY Sales Growth, Rolling 12-Month Sales, YTD Sales, Units Sold, Median Price Change and Price/SQM.
- Identified 29% YoY growth in auction sales, while regular and other sales declined 21% and family sales declined 75%.
- Analyzed regional sales concentration, identifying approximately 95bn sales in Zealand and 81bn in Jutland, and built interactive Power BI dashboards with scheduled refresh.

---

🧑‍💻 Skills Demonstrated

Data Analytics:
Data Cleaning • Exploratory Data Analysis • Business Analysis • KPI Development • Segmentation

SQL:
SELECT • WHERE • GROUP BY • Aggregations • Data Validation • Table Creation

Power BI:
Power Query • DAX • Interactive Dashboards • Slicers • Key Influencers • Scatter Plots • KPI Cards • Power BI Service

Business Intelligence:
Sales Performance • Pricing Analytics • Regional Analysis • Channel Analysis • Property Segmentation • Decision Support

Cloud:
Google BigQuery • Power BI Service

---

⭐ Project Outcome

The project demonstrates how a business can move from:

Raw Data → Clean Data → KPIs → Insights → Business Recommendations

rather than simply creating visual dashboards.

The key conclusion is that the business should scale the auction growth channel, recover declining sales types, protect high-volume markets, investigate weak regions and introduce property-level pricing benchmarks.
