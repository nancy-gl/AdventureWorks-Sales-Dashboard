# AdventureWorks-Sales-Dashboard

# Details of the report
## Data Setup:
  * With the best practice mindset, pushing all the data cleaning steps in the data source, used the following TSQL codes to clean the data in the SQL Server (used SQL Server 2019). 
  * Updated and cleaned the Database’s Dimension and Fact Tables.
    * [DIM_Date]
      *	Updated the Date column to include the recent dates with TSQL code.
      *	Cleansed the Date table to include only the required column and year with following TSQL code.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Dim_Date_SQL.png) 
      
    * [DIM_Product]
      *	Cleansed the Product table to include only the required column and joined the ProductCategory and ProductSubcategory tables with following TSQL code.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Dim_Product_SQL.png)
      
    * [DIM_Customer]
      * Cleansed the Customer Table to include only the required column and joined Geography Table to get the City column as shown:
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Dim_Customer_SQL.png)
    
    * [FACT_InternetSales]
      * Cleansed InternetSales Table and ensuring to bring only 2 years of Data during extraction.
      
      ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Fact_InternetSales_SQL.png)
      

## Data Model:
  * Imported all the CSV files (Reults of TSQL Codes saved to CSV file) to Power BI and created a Key Metrics Measure Table for all the measures.
  * The Data Model in Power BI looks like the following:
  
   ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Data%20Model.png)
   
      
## Visuals:
  * The Sales Dashboard with the visuals is as shown:
  
    ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Sales%20Dashboard.png)
  
  * Added Customer Details report as shown:
  
    ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Customer%20Details.png)
    
  * Added Product Details report as shown:
  
    ![](https://github.com/nancy-gl/AdventureWorks-Sales-Dashboard/blob/main/images/Product%20Details.png)

