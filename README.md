# DA_CLASS_PROJECT

## PROJECT TITLE: SALES PERFORMANCE ANALYSIS

### PROJECT OVERVIEW
This Data Analysis project aims to generate insight into the sales performance of a Retail Store over the past years. BY analysisng the various parameters in the data recieved. we gather enough insight to make reasonable decisions which enable us to tell compelling stories around our data from the insight gotten and to know the best performance from our data.

### DATA SOURCES
The primary source of data used here is a Data Sales csv and this is gotten from canvas.

### TOOLS USED
  . Microsoft Excel [downloade here]{htts://www.microsoftexcel.com}
  
 1, for Data cleaning.
 
 2, for Analysis.
 
 3, for Data Visualization.
 



### DATA ANALYSIS			
 
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




    ![image](https://github.com/user-attachments/assets/90c06c44-3300-49c6-be27-88be273a4ea9)


    

    
 
![image](https://github.com/user-attachments/assets/bd436759-ada2-4852-a2df-5030cdcca1dc)






![image](https://github.com/user-attachments/assets/0f5e45f1-f52e-4264-9ce6-6f845b0249ba)








![image](https://github.com/user-attachments/assets/90c06c44-3300-49c6-be27-88be273a4ea)


![image](https://github.com/user-attachments/assets/0c40162f-fd2d-4406-942c-5cb2bf586d1a)












![image](https://github.com/user-attachments/assets/23daf297-4069-4558-b995-69cf7f2ed2f4)




         


![image](https://github.com/user-attachments/assets/b92f2eb5-fb43-4e6b-a8a4-fec59a22f81a)










### SQL-STRUCTURED QUERY LANGUAGE

. SQL- Structured Query Language for Querying of Data.




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




### DATA VISAULZATION

. Power BI for Data Visualzation using it dashboard to visualized data. 

This is use to visualized the insights found in Excel and SQL.





![1730592768522](https://github.com/user-attachments/assets/914d4906-90b8-48fe-bdb0-c271b0a9cf04)






![1730592617598](https://github.com/user-attachments/assets/6752f05c-b2a8-43f1-90f9-15b60f3adb2a)











  ####     CUSTOMER DATA

  
  #### SUMMARY
  This project involues analysising customer data for a subscription service to identify segments and trends. the goal is to understand customer behavior, and track subscription types, 
  and identify key trends in cancellations and renewals.


### DATA SOURCES
The primary source of data used here is a Customer Data csv and this is gotten from canvas.


### TOOLS USED
  . Microsoft Excel [downloade here]{htts://www.microsoftexcel.com}
  
 1, for Data cleaning.
 
 2, for Analysis.
 
 3, for Data Visualization.



### DATA ANALYSIS

 
![image](https://github.com/user-attachments/assets/a6c6455a-64d9-4aad-a238-08827fa3e2b9)




![image](https://github.com/user-attachments/assets/d7d40dd9-f96d-47df-bd3b-a0942a9b5829)




![image](https://github.com/user-attachments/assets/52fd85af-63d8-40d1-946f-3165124697ae)




![image](https://github.com/user-attachments/assets/4040f97b-5c12-4b96-9d2a-33a0fbf74c7d)




![image](https://github.com/user-attachments/assets/f67e364a-91fd-4461-9803-76b84ab6140b)




![image](https://github.com/user-attachments/assets/af526f95-076a-4eaf-ae36-f4f26a26b116)







 



###   SQL- STRUCTURED QUERY LANGUAGE

. SQL- Structured Query Language for Querying of Data.





						---- CUSTOMER DATA----



SELECT * from [dbo].[CUSTOMER DATA 2]


				----to retrieve the total number of customers from each region---
    

select customerid, region, count(*) as number_visits from [dbo].[CUSTOMER DATA 2]

group by customerid,region

order by 2 desc


				----to fine most popular subscrpition type by the number of customer----

    select 
   
    subscriptiontype,
   
    count( DISTINCT customerid) AS customer_count

from [dbo].[CUSTOMER DATA 2]
  
   GROUP BY
       subscriptiontype
  
   ORDER BY 
   customer_count DESC
    

				 ----to fine customers who canceled their subscription within 6 months----
     

select

customerid,

 customername,

 subscriptionstart,

 subscriptionend,canceled

 from [dbo].[CUSTOMER DATA 2]

 subscriptions

 where
 canceled=1
 and datediff(month, subscriptionend, subscriptionstart) <=6
 
 
 
				---TO GET AVERAGE SUBSCRIPTION DURATION FOR ALL CUSTOMER---
    
 select
 
 AVG(DATEDIFF(DAY, 2022-01-31, 2024-12-31)) as average_subscription_duration
 
 from [dbo].[CUSTOMER DATA 2]
 
     suscriptions;

	 		----TO FINE CUSTOMERS WITH SUBSCRIPTION LONGER THAN 12 MONTHS-----
    
SELECT

 customerid,
 
 customername,
 
 subscriptionstart,
 
 subscriptionend,subscription_duration
 
 from [dbo].[CUSTOMER DATA 2]
 
 subscriptions
 
 where
 subscription_duration =1
 and datediff(month, subscriptionend, subscriptionstart) <=12

 

				----TO GET TOTAL REVENUE BY SUBSCRIPTION TYPE----
    
SELECT
     subscriptiontype,
     
      sum(revenue) as total_revenue
      
  from [dbo].[CUSTOMER DATA 2]
  
      subscriptions
      
	  group by
	  subscriptiontype
   
	  order by total_revenue DESC;


  				 ----TO GET TOP 3 REGIONS BY SUBSCRIPTION CANCELLATIONS.-----
       

SELECT region,

   customerid,
   
 customername,
 
 subscriptionstart,
 subscriptionend,canceled
 
 from [dbo].[CUSTOMER DATA 2]
 
 subscriptions
 
 where
 
 canceled=1
 and datediff(month, subscriptionend, subscriptionstart)<=3 


 					 ---- to get total number of active and canceled subscription----

       
SELECT

customerid,

customername,
     caneled(false)
     
	 count(subscriptiontype) AS totalcount  from [dbo].[CUSTOMER DATA 2]
  
	 subscriptions
  
	 group by 'canceled(false)'
  
Select

     subscriptions
     
	 COUNT(subscriptiontype) AS total  from [dbo].[CUSTOMER DATA 2]
  
	 group by canceled









  



  



###   DATA VISUALIZATION

 . Power BI for Data Visualzation.

 This is use to visualized the insights found in Excel and SQL.


 


 

![IMG_20241105_121743_251~2](https://github.com/user-attachments/assets/af84cd1a-2db7-449d-869f-496eedc3ce99)












![IMG_20241105_121452_971](https://github.com/user-attachments/assets/11be4bf7-8f64-446e-80dd-b46b3c4495e6)

 













