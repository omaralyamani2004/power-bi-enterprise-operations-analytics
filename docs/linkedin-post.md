# LinkedIn post draft

I’m pleased to share an Enterprise Operations Analytics dashboard built in Power BI using the Adventure Works training dataset.

The report brings together executive sales performance, customer behavior, workforce analysis, and inventory context in a role-oriented reporting experience.

What I implemented:

• Power Query transformations for clean, model-ready tables  
• A star-schema-oriented semantic model with date, customer, product, territory, employee, and fact tables  
• DAX measures for Total Revenue, Total COGS, Gross Profit Margin, YoY Revenue Growth, Total Customers, Average Orders per Customer, Returning Customers, and Average Spending  
• Interactive slicers and cross-filtering for date, geography, product, customer attributes, and department  
• Executive KPI design focused on moving from headline performance to actionable business questions  
• A QA review that validates totals, filter context, and the reliability of customer-level insights before publication

One example of the type of insight the dashboard surfaces: the current Commercial Sales view shows $80.45M in revenue, while Bikes contribute approximately 82.4% of total revenue but display a -1.49% gross margin. That contrast highlights a potential concentration and profitability risk that deserves investigation beyond revenue growth alone.

The Customer Analysis page also shows how customer volume, order frequency, returning-customer behavior, geography, and customer segments can be analyzed together.

I’m sharing the methodology, curated measure catalog, screenshots, and QA notes in the GitHub repository:

[GitHub repository link]

#PowerBI #DAX #PowerQuery #BusinessIntelligence #DataAnalytics #AdventureWorks

