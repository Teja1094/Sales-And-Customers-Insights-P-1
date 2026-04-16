Sales And Customers Insights 

Power BI Project Documentation

         Sales & Customer Insights Dashboard
                     
 INDEX:
1. Project Overview
2. Data Model Overview 
3. Data Preparation
4. Key Metrics (KPIs)
5. DashBoard Pages
6. Visualization Used
7. Business Insights Delivered
8. Key Features
9. Challenges and Solutions
10. Conclusions
11. Future Enhancements


1. Project Overview
   
This project is designed to analyze and monitor business performance across sales, profit, customers, returns, and shipping operations. The dashboard provides decision-makers with a centralized, interactive view of key metrics.
Objectives
• Track overall business performance (Sales, Profit, Orders)
• Understand customer behavior and segmentation
• Analyze regional performance
• Monitor returns and shipping efficiency
• Identify trends and growth opportunities

3. Data Model Overview
   
Schema Type: Star Schema
The data model follows a star schema design, ensuring:
• High performance
• Easy filtering and slicing
• Clear separation of fact and dimension tables

Tables Used

   Fact Table
   
Orders Table (Central Table)
Contains transactional data:
• Order ID
• Order Date
• Customer ID
• Sales, Profit, Quantity
• Discount, Cost, Net Price
• Product & Geography details
This table drives all calculations and aggregations.

Dimension Tables

 1. People Table
    
• Person
• Region
Used for mapping sales ownership and regional analysis

3. Returns Table
   
• Order ID
• Returned (Yes/No)
• Return Rate %
• Total Returns
Used to analyze return behavior and product issues

Relationships

• Orders → People (Region-based relationship)
• Orders → Returns (Order ID relationship)

Filter Direction

• Single Direction Filtering
• From dimension → fact
• Improves performance and avoids ambiguity

3. Data Preparation
   
Derived Columns Created
• Price after Discount
• Cost Price Calculations
• Customer-related attributes
• Region/Category groupings

DAX Measures Created

• Total Sales - Total Sales = SUM(Orders[Netprice])
• Total Profit - Total Profit = SUM(Orders[profit amt])
• Total Orders - Total Orders = COUNT(Orders[Order ID])
• Total Customers - Total Customers = DISTINCTCOUNT(Orders[Customer ID])
• Profit Margin % - Profit Margin% = DIVIDE(SUM(Orders[profit amt]), SUM(Orders[Netprice])) * 100
• YoY Growth - YOY Growth% = DIVIDE([YOY Sales Growth],[Sales LY])
• YoY Sales Growth - TOTALYTD([Total Sales], Orders[Order Date])
• Return Rate % - ReturnRate% = DIVIDE([Total Returns], [Total Orders])



4. Key Metrics (KPIs)
   
• Total Sales
• Total Profit
• Total Orders
• Total Customers
• Profit Margin %
• Return Rate
• Year-over-Year Growth
These KPIs provide a quick executive summary of business performance.

6. Dashboard Pages
   
1. Executive Overview
   
Purpose: High-level performance snapshot
Key Visuals:
• KPI Cards (Sales, Profit, Orders, Customers)
• Trend Line (Sales over time)
• YoY Growth indicators
Helps leadership quickly assess performance.

3. Sales & Profit Analysis
   
Purpose: Deep dive into revenue and profitability
Key Insights:
• Sales by Category & Sub-category
• Profit vs Sales comparison
• High-performing products
Identifies profitable and loss-making areas.

5. Geography Analysis
   
Purpose: Regional performance tracking
Key Visuals:
• Sales by Region/State
• Map visualization
• Region-wise profitability
Helps identify strong and weak markets.


7. Segment Analysis
   
Purpose: Customer segmentation insights
Segments Used:
• Consumer
• Corporate
• Home Office
Insights:
• Sales by segment
• Profit contribution
• Customer behavior patterns

9. Returns Analysis
    
Purpose: Monitor product returns
Key Insights:
• Return Rate %
• Returned Orders
• Impact on profit
Helps identify product or logistics issues.


11. Shipping Analysis
    
Purpose: Evaluate delivery performance
Key Insights:
• Ship Mode usage
• Delivery trends
• Cost vs efficiency
Helps optimize logistics strategy.

6. Visualizations Used
   
• KPI Cards
• Line Charts (Trend Analysis)
• Bar Charts (Comparisons)
• Map Visuals (Geography)
• Matrix (Heatmaps with conditional formatting)
• Scatter Charts (Correlation analysis)

8. Business Insights Delivered
   
• Identification of high-revenue regions
• Understanding of customer segments driving growth
• Detection of high return-rate products
• Profitability gaps across categories
• Shipping inefficiencies


10. Key Features
    
• Interactive filtering (Date, Region, Segment)
• Drill-down capabilities
• Clean and user-friendly layout
• Real-time insights

12. Challenges & Solutions
    
ChallengeSolutionData inconsistencyData cleaning & transformationComplex calculationsEfficient DAX measuresPerformance issuesStar schema + single filter directionReturn trackingIntegrated Returns table

14. Conclusion
    
This dashboard provides a comprehensive 360° view of business performance. It enables stakeholders to:
• Make data-driven decisions
• Improve profitability
• Optimize operations
• Enhance customer satisfaction

16. Future Enhancements
    
• Predictive analytics (forecasting)
• Customer churn analysis
• Inventory optimization
• Advanced drill-through pages

