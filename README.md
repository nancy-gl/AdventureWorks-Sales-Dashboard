# Executive Dashboard

# Details of the dashboard
## Data Setup:
  * With the best practice mindset, pushing all the data cleaning steps in the data source, used the following TSQL codes to clean the data in the SQL Server (used SQL Server 2019). 
  * Updated and cleaned the Database’s Dimension and Fact Tables.
    * [DIM_Date]
      *	Updated the Date column to include the recent dates with TSQL code.
      *	Cleansed the Date table to include only the required column and year with following TSQL code.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DimDate2.png)
      
    * [DIM_Product]
      *	Cleansed the Product table to include only the required column and joined the ProductCategory and ProductSubcategory tables with following TSQL code.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Dim_Product_SQL.png)
      
      *	Made changes to because joining the product, category and subcategory resulted in many-to-many relationship so changed the TSQL code to avoid the many-to-many relationship and created the model with many-to-1 relationship.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DimProduct2-2.png)
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DimSubcategory2.png)
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DimCategory2.png)
      
    * [DIM_Territory]
      * To analyse the regional sales data joined the tables Geography and SalesTerritory as shown:
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DimGeography2.png)
    
    * [FACT_Sales]
      * Cleansed InternetSales Table and ensuring to bring 10 years of Data during extraction.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/FactSales.png)
      

## Data Model:
  * Imported all the CSV files (Reults of TSQL Codes saved to CSV file) to Power BI and created a Key Metrics Measure Table for all the measures.
  * The Data Model in Power BI looks like the following:
  
   ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/DataModel2.png)
   
      
## Reporting and Visuals:
  * The Executive Dashboard with the visuals is as shown:
  
  ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/ExecutiveDashboard.png)
  
  * Calculated [Total Sales], [LY Sales], [YoY Sales], [YoY Growth] for the sales trends
  * The DAX used are as follows:
  
          * i.	Total Sales = SUM(FactSales[SalesAmount])  
          * ii.	LY Sales = CALCULATE ([Total Sales], DATEADD(DimDate[Date], -1, YEAR))
          
  * Note: Can also use SAMEPERIODLASTYEAR(DimDate[Date]) and PREVIOUSYEAR(DimDate[Date])  functions which returned the same results.

         * iii.	YoY Sales = [Total Sales] - [LY Sales]
         * iv.	YoY Sales % = DIVIDE ([YoY Sales], [LY Sales], "-")


## [Click here to view the dashboard on the web.](https://app.powerbi.com/links/KDcVbYJwXU?ctid=3fb43f9e-f396-473f-bdb4-7b116a3228ce&pbi_source=linkShare) 

## [Click here to view the dashboard on the web.](https://app.powerbi.com/reportEmbed?reportId=3c2ac147-a5a4-481e-826f-30593864f9fc&autoAuth=true&ctid=3fb43f9e-f396-473f-bdb4-7b116a3228ce&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXdlc3QtdXMtYi1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9)
