#  Marketing Campaign Performance & Customer Segmentation Dashboard

[![View on GitHub](https://github.com/peteo0098/Marketing-Campaign-Performance-Customer-Segmentation-Dashboard)

## Project Overview
Project Overview This project concentrates on examining customer data and marketing campaign results to pinpoint major purchasing patterns, ideal customer groups, and the success of campaigns. The ultimate deliverable is an interactive Power BI dashboard that offers practical insights for the marketing team to improve future budget distribution.

![Marketing Dashboard](https://github.com/peteo0098/Marketing-Campaign-Performance-Customer-Segmentation-Dashboard/blob/main/Marketing%20Dashboard.png)

##  Business Problem
Business Problem The marketing department required a straightforward, high-level summary of their customer base and the return on investment from their recent campaigns. This dashboard addresses key questions such as: 
* Which customer demographics (Education, Marital Status, Age) produce the highest revenue?
*  Is there a direct link between customer income and overall expenditure?
*  Which marketing campaigns achieved the highest acceptance rates?
* What are the most favored purchasing channels (Web, Store, Catalog)?

## Technical Stack & Skills Demonstrated
**Tool:
**Power BI Desktop 
**Data Cleaning & Transformation:** Power Query (Handling outliers, unpivoting flat files) * 
**Data Modeling:** Relational Modeling (Star Schema) * 
**Calculations:** DAX (Custom Measures, Calculated Columns) * 
**Data Visualization:** KPI Cards, Scatter Plots, Donut Charts, Histograms with Binned groups  

##  Data Transformation & Modeling (The "Under the Hood" approach)
The original dataset from Kaggle was provided as a single, wide flat file. To ensure accurate calculations and avoid row duplication errors (many-to-many relationship issues), I transformed the flat file into a robust **Star Schema**:   
1. **Fact Table:** Kept the main `Marketing Campaign` table for customer demographics and core metrics.
2. **Dimension Tables:** Extracted and unpivoted campaign responses into a `Dim_Campaigns` table and purchasing channels into a `Dim_Purchases` table.
3. Linked them via a 1-to-Many relationship using a unique Customer `ID`.

![Data Model](https://github.com/peteo0098/Marketing-Campaign-Performance-Customer-Segmentation-Dashboard/blob/main/Marketing%20model%20view.png)

## Key DAX Measures Created
* `Total Revenue = SUM(Marketing_Campaign[MntTotal])`
* `Total Purchases = SUM(Dim_Purchases[Number of Purchases])`
* `Total Responses = SUM(Dim_Campaigns[Accepted])`
* `Age = YEAR(TODAY()) - 'Marketing Campaign'[Year_Birth]` (Grouped into 10-year bins for histogram analysis)
* `Total Revenue = SUM(Marketing_Campaign[MntTotal])`
* `Total Purchases = SUM(Dim_Purchases[Number of Purchases])`
* `Total Responses = SUM(Dim_Campaigns[Accepted])`
* `Age = YEAR(TODAY()) - 'Marketing Campaign'[Year_Birth]` (Grouped into 10-year bins for histogram analysis)  
##  Key Insights & Findings
1. **Revenue Drivers:** Customers with a "Graduation" level of education and those who are "Married" or living "Together" form the most profitable demographic.
2. **Income vs. Spend:** A strong positive correlation exists between income and total spend, with clear outliers effectively filtered out.   
3. **Channel Preference:** Purchases made in-store consistently outperform those made through catalog and web channels.   
4. **Campaign Effectiveness:** Campaign 4 and Campaign 3 achieved the highest success, whereas Campaign 2 performed significantly worse.    

## Files in this Repository
* `Marketing Dashboard.pbix` - The fully functional interactive Power BI file containing the data model and visuals.
* `Marketing Dashoard.png` - A high-resolution static export of the final dashboard.
* `Marketing model view.png` - A screenshot showcasing the Star Schema data model.

---
*Created by [peteo0098](https://github.com/peteo0098)*
