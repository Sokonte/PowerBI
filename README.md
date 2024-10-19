### INTRODUCTION
This project conducts an in-depth analysis of sales data encompassing various branches, product types, quantity sold, time of sale, date of sale, sales discounts, and unit prices. The primary objective is to derive actionable insights on total revenue, total quantity purchased, overall number of transactions, revenue distribution across different branches, identification of the top 7 best-selling pizza types, understanding the least selling pizza types, revenue trends across different date periods, revenue patterns by day of the week, and the overall revenue trend.

### DATA COLLECTED
The dataset includes the following key column
1. Trade Date
2. Branch
3. Pizzatype
4. Unit price
5. Quantity
6. Sales discount
7. Time

### PROJECT OBJECTIVE
 This project aims to address the following analyses:
1. Total Sales Revenue: Calculate the total sales revenue by multiplying the quantity by  price per unit and the discount for each entry to understand the overall sales performance.
2. Sales Trends Over Time: Use the date and time columns to analyze sales trends over different time periods (daily, weekly, monthly, seasonal) to identify peak sales days/times and periods of low sales.
3. Branch Performance Comparison: Compare sales across different branches to determine which locations are performing better. This can help identify top-performing branches and those that may need additional support.
4. Product Performance: Determine which products generate the most revenue or are sold most frequently using the product column. This can help in managing inventory and marketing efforts.
5. Top-Selling Products: Identify which products are sold most frequently (unit sold) to maintain adequate stock levels of materials.
6. Slow-Moving Inventory: Spot products with low sales that may require special promotions.
7. Branch-Level Stock Analysis: Understand which branches sell particular products faster and require frequent restocking of material.
8. Sales Patterns by Time of Day: Analyze the time column to find peak hours for sales. This can help optimize staffing and inventory levels during busy hours.

### KEY METRICS
1. Total Revenue: This represents the overall income generated from sales, calculated as the sum of the revenue column.
2. Total Units Sold: This denotes the cumulative number of units sold, obtained by summing the units sold column.
3. Discount Impact on Revenue: This involves analyzing how discounts influence overall revenue.
4. Time-Based Analysis: This entails assessing sales performance by different time intervals (e.g., seasonality effects) to identify trends and patterns.
5. Sales Growth Rate: This measures the percentage increase in sales revenue over a specific period (e.g., month-over-month, year-over-year).
6. Sales Performance Over Time: This involves analyzing trends over different time frames (daily, weekly, monthly) to identify peak sales periods.

### TOOLS AND METHODS
### Data Preparation and Cleaning with Power Query
- Data Import: Import data from Excel
- Data Cleaning: Ensure unique records by removing duplicates, excluding irrelevant data through row filtering, and replacing or removing missing values if necessary.
- Data Transformation: Ensure consistency by changing data types (e.g date, number, text) and improving data structuring by merging columns.
- Data Normalization: Establish relationships between tables by defining primary and foreign keys.

### Data modeling
- Establish Relationships: Enable efficient querying and accurate visualizations by creating relationships between tables (one-to-many, many-to-many).
- Build a Date Table: Create a Date table with columns like Year, Quarter, Month, Day, etc., and relate it to the main data for time-based calculations (e.g., year-to-date, month-to-date).
- Use Star Schema or Snowflake Schema: Connect a sales fact table to dimension tables (e.g. Sales table linked to Product, Branch, and Date tables).

### CALCULATION AND ANALYSIS WITH DAX (Data Analysis Expressions)
- Creating Measures and Calculated Columns:
- Measures: Empower dynamic calculations based on report filters (e.g. total revenue, total quantity, and transaction).
- Calculated Columns: Utilize static calculations that don’t change based on report filters (e.g. Revenue, Day of week, Period of day).
### FORMULA USED:
- Revenue Calculation: Revenue = SUM(Sales[Quantity]) * SUM(Sales[Price per Unit])*(1-Sales Discount)
- Day of week: format([Date],"dddd")
- Period of day: IF(HOUR('Sales Fact'[Time])<12,"Morning",IF(HOUR('Sales Fact'[Time])<16,"Afternoon","Evening"))
- Total revenue: SUM('Sales Fact'[Revenue])
- Total of quantity: SUM('Sales Fact'[Quantity])
- Total transaction: COUNT('Sales Fact'[Transaction ID])

### DATA VISUALIZATION
- Bar/Column Charts: Effectively compare quantities across categories.
- Line Charts: Clearly display trends over time.
- Pie Charts: Provide insights into percentage distribution.
- Tree Map: Offer detailed data views.
- Using Slicers and Filters: Enhance user-driven filtering by adding slicers (e.g., period of day). 

### RECOMMENDATIONS
1.	Focus on branch-specific strategies
 - The best-selling branch should have a meeting to speak on how they make large sales and what they do differently
2.	Optimize operations by time of day
 - More hands-on deck in the morning and afternoon since there’s a higher purchase at that time
3.	Promote top-selling pizza
 - Put in more Revenue in the top-selling pizza to generate more Revenue
4.	Revamp, Promote or Remove the least-selling pizza
 - A sort of promo to the least pizza type to boost the revenue and review the recipe of the pizza. If all these don’t work, it should be removed.
5.	Day-of-the-week promotions
 -  A promo for Wednesday and Friday to boost sales or have a discount during those days.

   
