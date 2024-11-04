# LITA_PROJECT_CAPSTONE-2

### Project Title: Customer Segementation for a Subscription Service

### Project Overview

This customer segementation analysis aims to identify distinct groups within the subscription service and customer subscription type, enabling data-driven decisions to enhance customer experiences, optimize marketing strategies and increase oveerall subscription value.

### Data sources.

The primary sources of this project inludes; customer relationship management (CRM) system, customeer database and mobile app or web analytics tools.

### Tools used

the tools used for this project are;
Microsoft excel for data cleaning
SQL for query writing
Powerbi for visualization and
Github for documentation
Data cleaning
data cleaning involves several processes. to ensure data accuracy, completeness and consistency, here is a step-by-step process.

### Data cleaning
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

1.  Here, i'm going to analyze the customer data using pivot tables to find the subscription patterns.

### subscription distribution by region

![subscription by region](https://github.com/user-attachments/assets/6287b94c-026a-486f-8631-fa81f28b13a4)

This pivot table explains the regions that have the most subscribers and the subsription type that are popular in each region.


### subscription growth over time

![subscription growth](https://github.com/user-attachments/assets/d0858b4e-21a5-4a98-8a3f-a4604cf60dcf)

This pivot table above explains how subscription growth vary by month/quarter and how subscription types have steady growth.

### Cancelation Rates

![cancelation rate](https://github.com/user-attachments/assets/6c29932f-d0ee-4955-8e8b-7780791aec0a)

This explains the subsription types that have higher cancelation rates.


### Revenue Analysis.






2. Here, i'm goin to calculate the average subscription duration and identigy the most popular types


### average subscription duration

![avg subsription duration](https://github.com/user-attachments/assets/c225f6fb-1999-427d-9e66-dbbe3328c353)

The above table explains how long customers typically subscribes.





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
            SELECT COUNT (*)
            FROM [dbo]. [lita_project 2]
            WHERE canceled =0
             ```


   #### Canceled subscribers


          ```SQL
             SELECT COUNT(*)
             FROM [dbo]. [lita_project 2]
             WHERE canceled = 1
             ```
   










       

