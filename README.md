# DA_CLASS_PROJECT

## PROJECT TITLE: SALES PERFORMANCE ANALYSIS

### PROJECT OVERVIEW
This Data Analysis project aims to generate insight intothe sales performance of a Retail Store over the past years. BY analysisng the various parameters in the data recieved. we gather enough insight to make reasonable decisions which enable us to tell compelling stories around our data from the insight gotten and to know the best performance from our data.

### DATA SOURCES
The primary source of data used here is a Data Sales csv and this is gotten from canvas.

### TOOLS USED
  . Microsoft Excel [downloade here]{htts://www.microsoftexcel.com}
  
 1, for Data cleaning.
 
 2, for Analysis.
 
 3, for Data Visualization.
 
  
  
  . Power BI for Data Visualzation.

  
               TOTAL REVENUE BY REGION
               
![image](https://github.com/user-attachments/assets/9321c242-d100-4468-8d5b-04ac7a2fc26f)


             TOTAL REVENUE BY PRODUCT
             
![image](https://github.com/user-attachments/assets/b313264e-d602-4e56-8e3e-eb8c88a66475)


               TOTAL REVENUE BY MONTH 
               
![image](https://github.com/user-attachments/assets/db48a912-5d6c-47e2-8e8d-3d0d57783596)


            
             TOTAL PRODUCT BY UNITPRICE 
![image](https://github.com/user-attachments/assets/80a346bc-d36c-4a74-bfb1-d0eac45530d6)



                TOTAL PRoDUCT BY UNITPRICE AND REGION 	
 
![image](https://github.com/user-attachments/assets/038b84aa-f806-49cc-a36d-490ca4b6e82b)


             REGION BY AVERAGE SALES 	
 
![image](https://github.com/user-attachments/assets/6c915df3-5383-4c58-b1b3-ce043b367cec)


           AVERAGES SALES BY YEARS 	
 
![image](https://github.com/user-attachments/assets/bd436759-ada2-4852-a2df-5030cdcca1dc)



![image](https://github.com/user-attachments/assets/23daf297-4069-4558-b995-69cf7f2ed2f


![image](https://github.com/user-attachments/assets/0f5e45f1-f52e-4264-9ce6-6f845b0249ba)



![image](https://github.com/user-attachments/assets/01bf6018-ec66-4ba2-beb7-e1d473f42534)         ![image](https://github.com/user-attachments/assets/23daf297-4069-4558-b995-69cf7f2ed2f



![image](https://github.com/user-attachments/assets/0f5e45f1-f52e-4264-9ce6-6f845b0249ba)






![image](https://github.com/user-attachments/assets/23daf297-4069-4558-b995-69cf7f2ed2f4)


         


![image](https://github.com/user-attachments/assets/b92f2eb5-fb43-4e6b-a8a4-fec59a22f81a)




. SQL- Structured Query Language for Overying of Data.



CREATE DATABASE FLOR_DB


select *from [dbo].[Copy of LITA_Capstone_Dataset(4)csv]



                -----To get Revenue By Product------
                
select sum(revenue) AS totalsale From[dbo].[Copy of LITA_Capstone_Dataset(4)csv]


                  ----find the number of sales transactions in each region---
                  
select region, count(*) AS Numberofsalestransactions

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

group by region


              ----calculate total revenue per product---
              
select product, SUM(Revenue) AS Revenue

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

group by product


                    ----Retrieve the total sales for each product category---
                    
select product, SUM(Revenue) AS TOTALSALES

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

group by product


                  ----find the Highest-selling product by total sales value----
                  
select top 5 product, SUM(revenue) AS Highestsellingproduct

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

group by product

ORDER BY 2 DESC

                            -----To get Revenue By Product------
                            
select sum(revenue) AS totalsale

From[dbo].[Copy of LITA_Capstone_Dataset(4)csv]



               
                ----calculate monthly sales totals for the current year---

SELECT
     Year(Orderdate) AS year,
 
  MONTH(OrderDate) AS month,
  
   SUM(Revenue) AS Totalsales
  
   from [dbo].[Copy of LITA_Capstone_Dataset(4)csv]
  
   WHERE
       YEAR(orderdate) = YEAR((2024-01-30))
   
    GROUP BY
        YEAR(OrderDate),
              MONTH(orderdate)
    ORDER BY
          YEAR(orderdate),
          MONTH(OrderDate);
     

              
              ----find the top 5 customers by total purchase---
              
select top 5 customer_id, sum(revenue) AS totalproduct

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

group by customer_id

order by 2 desc


            ----identify products with no sales in the last quarter---


SELECT
   
    p.productid,
	
 p.productname
 
 FROM [dbo].[Copy of LITA_Capstone_Dataset(4)csv]
    
     products p

LEFT JOIN
    
     sales s ON p.products = s.products
	
  AND s.saledate >= '2023-04-30'(QUARTER, -1,)

 WHERE  
      s.productname IS NULL
  
  

               -----Calculate the percentage of total sales contributed by each region----

               
select region,  sum(quantity) as total_quantity, (sum(quantity) / (SELECT SUM(quantity) totalsales) * 100) AS Percentage

from[dbo].[Copy of LITA_Capstone_Dataset(4)csv]

GROUP BY region

ORDER BY SUM(quantity) desc;




. Power BI for Data Visualzation.



















