# LITA_PROJECT_CAPSTONE-2

### Project Title: Customer Segementation for a Subscription Service

[Project Overview](#Project-Overview)

[Data sources](#Data-sources)

[Tools used](#Tools-used)

[Data cleaning](#Data-cleaning)

[exploratory data analysis (EDA)](#Exploratory-data-analysis (EDA))

[Data Analysis](#Data-Analysis)


This customer segementation analysis aims to identify distinct groups within the subscription service and customer subscription type, enabling data-driven decisions to enhance customer experiences, optimize marketing strategies and increase oveerall subscription value.

### Data sources.

The primary sources of this project inludes; customer relationship management (CRM) system, customeer database and mobile app or web analytics tools.

### Tools used

the tools used for this project are;
-  Microsoft excel for data cleaning
-  SQL for query writing
-  Powerbi for visualization and
-  Github for documentation


### Data cleaning
data cleaning involves several processes. to ensure data accuracy, completeness and consistency, here is a step-by-step process.
-  handling missing files
-  identify missing values (e.g, NULL, blank, NA).
-  decide on replacement stategies (e.g, mean, median, imputation).
-  replace missing values
-  data normalization
-  standardize date formats
-  convert categorical variables into numerical variables
-  error detection and correction data transformation

 ### exploratory data analysis (EDA)
  EDA involves examining and summarizing data to understand patterns, trends and corrections. here is a comprehensive EDA checklist.
-  what are the top-selling products/category
-  which regions/territories generate most most sales
-  how do sales vary by season/holiday
-  which customer segments drive most sales
-  what marketing channels are most effective

 
  
  ### Data Analysis

  ### EXCEL



1.  Here, i'm going to analyze the customer data using pivot tables to find the subscription patterns.

### subscription distribution by region

![subscription by region](https://github.com/user-attachments/assets/6287b94c-026a-486f-8631-fa81f28b13a4)

This pivot table explains the regions that have the most subscribers and the subsription type that are popular in each region.


### subscription growth over time

![subscription growth](https://github.com/user-attachments/assets/d0858b4e-21a5-4a98-8a3f-a4604cf60dcf)

This pivot table above explains how subscription growth vary by month/quarter and how subscription types have steady growth.

### Cancelation Rates

![cancelation rate](https://github.com/user-attachments/assets/88e9ce54-081a-45a1-a1d4-3ee48ca24d83)

This explains the subsription types that have higher cancelation rates.


### Revenue Analysis.

![revenue](https://github.com/user-attachments/assets/37e02644-7fc3-4f7a-ba0c-27e3b2562007)


This table shows the sum of revenue generated by each region according to the customers subscription type






2. Here, i'm going to calculate the average subscription duration and identify the most popular types


### average subscription duration

![avg subsription duration](https://github.com/user-attachments/assets/c225f6fb-1999-427d-9e66-dbbe3328c353)

The above table explains how long customers typically subscribe


### Popular subscription type


![popular sub type](https://github.com/user-attachments/assets/52b2016c-f00f-48cf-8b37-28c84e187913)


Given the explanation of this table above, the popular subscription type is BASIC because it has the hihest number of subscribers.







3. here, i will calculate the percentage of revenue generated by each region



![revenue %](https://github.com/user-attachments/assets/31bb5e8e-bdd9-430e-ad70-4d8cf12e7ba9)


The table above shows the percentage of revenue generated by each region




### SQL (Structured Query Language)


1.  here, i'm going to retrieve the no of customers from each region

     ```SQL
        SELECT region, COUNT (customerid) AS total_customers
        FROM [dbo]. [lita_project 2]
        GROUP BY region
        ```

     
 2.  here, i will find the most popular subscription type by the no of customers.

       ```SQL
           SELECT TOP 1 subscriptiontype, COUNT (customerid) AS number_ of_ customers
           FROM [dbo]. [lita _project 2]
           GROUP BY subscriptiontype
           ORDER BY number_ of_ customers
           ```

3.  here, i will find customers who canceled their subscription within 6 months.

      ```SQL
         SELECT COUNT(*) FROM [dbo]. [lita_project 2]
         WHERE canceled = 1
          AND
         DATEDIFF(month, subscriptionstart, subscriptionend) <= 6
         ```

4.  here, i will calculate the average subscription duration for all customers.


     ```SQL
        SELECT AVG(subscription duration) AS average_subscription duration
        FROM [dbo]. [lita_project]
        ```


 5.  here, i will find customers with subscriptions longer than 12 months

      ```SQL
          SELECT COUNT(*) FROM [dbo]. [lita_project 2)
          WHERE
           DATEDIFF(month, subscriptionstart, subscriptionend) >12
            ```

6.  here, i will calculatetotal revenue by subscription type.

     ```SQL
         SELECT subscriptiontype, SUM(revenue) AS total_revenue
         FROM [dbo]. [lita_project 2]
         GROUP BY subscriptiontype
          ```

7.  here, i will find the top 3 regions by subscription cancelations.

     ``` SQL
         SELECT TOP 3 region, COUNT(*) AS cancelation_count
         FROM [dbo]. [lita_project 2]
         WHERE canceled = 1
         GROUP BY region
         ORDER BY cancelation_count DESC
          ```



8.  Here, i will find the total no of active and canceled subscriptions.

   #### Active subscribers

        ```SQL
         select count (*)
         from [dbo].[lita-project 2]
         where Canceled =0
         ```


   #### Canceled subscribers
     
      
      ```SQL
      select count (*)
      from [dbo].[lita-project 2]
      where Canceled =1
        ```

### Power Bi

Here, i'm going to build a powerbi dashboard that visualizes key customer segments, cancelations and subscription trends with slicers for interactive analysis

### customer segments

![customer segments](https://github.com/user-attachments/assets/137bf8b3-dc46-4ace-8725-68eb5bb87732)


This picture above explains customer trends with their subsription type and their region with a slicer for a better analysis

### Cancelation trends


![cancelation trends](https://github.com/user-attachments/assets/58336129-8cb4-47e9-a3da-42ce3df8969e)


This pie chart explains the cancelation trends of subscribers with slicers showing the active and canceled subscriber for more analysis


### Subscription trends


![subscription trends](https://github.com/user-attachments/assets/f7bc92d8-0bf7-4b5d-a384-3eb21a3ad3ac)


This pie chart explains the subscription trends of customers with their region, subscription and the date of their subscription

   In conclusion, my analysis of the customer dataset revealed valuable insights into customer behaviour, preference and revenue patterns. 
 this segmentation helped identify disinct customer groups, enabling targeted strategies to enhance customer retention, acquisition and revenue growth.






       

