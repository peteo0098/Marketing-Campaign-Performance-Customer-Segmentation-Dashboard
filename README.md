Marketing Campaign Performance & Customer Segmentation Dashboard 

![View on GitHub](https://github.com/peteo0098/Marketing-Campaign-Performance-Customer-Segmentation-Dashboard.png)

### Overview of the Project The primary goal of this project is to provide an analysis of customers and their responses to marketing through data analysis of customer and marketing campaign results. We will be creating an interactive Power BI dashboard which will enable the marketing team to use this data to inform their future budget distribution decisions.

Business Problem
  
  Concerns With Marketing Department The marketing teams need to know more about their customers and how successful their recent marketing efforts are. The dashboard is designed to provide answers for several important questions: • Who are the customers (by demographic) that generate the greatest revenue? • Is there a relationship between customers’ income level and that customers’ total spending? • Which marketing campaigns had the highest acceptance rates? What are the most preferred purchasing channels (Web, Store, Catalog)? Tools Used & Skills Table Tool: Power BI Desktop Data Cleaning/Transformation: Power Query (outlier-handling, unpivoting flat files) * Data Modelling: Relational Modelling (Star Schema) * Calculations: DAX (Custom Measures, Calculated Columns) * Data Visualization: KPI cards, Scatter Plots, Donut Charts, Histograms with Binned groups
  
  Data Transformation & Modeling (The "Under the Hood" approach)
  
  The data from kaggle came as one wide spreadsheet. To remove any issues when calculating values, and to ensure that I did not have duplicated rows (due to many-to-many relationships), I converted the wide flat file into a very robust Star Schema: 1. Fact Table: The main Marketing Campaign table was kept for customer demographics and base metrics. 2. Dimension Tables: I created two different Dimension tables: Dim_Campaigns for the unpivoted set of responses for campaign responses, and Dim_Purchases for channels used to purchase. In a one-to-many (1:N) relationship with a unique customer identifier through customer ID value; illustrated below through the marketing model view. 
  
  Created DAX Measures * Total Revenue = sum of Marketing Campaign(MntTotal) * Total Purchases = sum of Dim Purchases(Number of Purchases) * Total Responses = sum of Dim Campaigns(Accepted) * Age = YEAR(TODAY()) - 'Marketing Campaign'[Year_Birth] (Grouped in 10 year bins for histogram analysis.)
  
  Here are the key findings and insights regarding the study: 1. The highest source of revenue comes from customers who have attained "graduated" levels of education as well as customers who are either "married" or living "together". 2. There is a significant and positive relationship (correlation) between income and total amounts spent by participants – as seen through identifying clearly defined patterns across several very distinct outlier types that could have caused a change in the results (e.g., aberrant behaviours).3. In-Store Purchases vs. Mail Order Purchases - Purchases In-Store Continue to Exceed Purchases from the Mail Order Channel. 4. Success of Each Campaign - Campaign 4 and Campaign 3 were the most successful, while Campaign 2 had substantially lower success rates than the other two campaigns.
  
  This Repository Contains Files: 1. The complete interactive Power BI model with data and visuals is in Marketing Dashboard.pbix 2. The final version of the dashboard image is in Marketing Dashoard.png. It has been exported as a high-quality image.

Marketing model view.png - A screenshot showcasing the Star Schema data model.


Created by peteo0098
