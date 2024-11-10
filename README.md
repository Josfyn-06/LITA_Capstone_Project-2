## LITA_Capstone_Project
My first practical application of data analysis concepts learned during my studies with Incubator Hub covering data cleaning, data querying, visualisation and insights extraction using Microsoft Excel, SQL and Power BI.

## Project Title: Customer Data

### Table of Contents
[Project Overview](#project-overview)

[Dataset](#dataset)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualisation](#data-visualisation)

[Insights](#insights)

[Recommendation](#recommendation)

### Project Overview
This project aims to analyse customer data for a subscription service, uncovering valuable insights into customer behaviour, subscription patterns and trends in cancellations and renewals. Leveraging Microsoft Excel, SQL and Power BI, this analysis seeks toinform data-driven decisions and optimise subscription services.

### Dataset
The dataset contains the following columns:
- *CustomerID*: Unique identifier foe each customer
- *Customer Name*: Name of each customer who subscribed
- *Region*: Geographical area where the subscription order was made
- *Subscription Type*: The subscription plan the customer is subscribed to
- *Subscription Start*: Start date of the customer's subscription
- *Subscription End*: End date pf the customer's subscription
- *Canceled*: Shows if subscription was cancelled before subscription end
- *Revenue*: Revenue generated from each subscription that was purchased
- *Subscription Duration*: Duration of each subscription in days, calculated as Subscription End- Subscription Start

### Data Sources
The primary source of data used here is Customer Data.csv and this is an open source data that can freely be downloaded from an open source online suvh as Kaggle or FRED, though this dataset was given by the Incubator Hub.

### Tools Used
- *Microsoft Excel*: for data cleaning, analysis and visualisation
- *SQL (Structured Query Language)*: for data querying
- *Power BI*: for visualisation

### Data Cleaning and Preparation
In this phase of my analysis, i performed the following actions:
- *Data Loading*: Loaded the dataset
- *Blank Value Check*: Verified the dataset for blank values
- *Data Type Conversion*: Converted specified columns to text format for consistency
- *Data Standardization*: Reformatted date columns to YYYY-MM-DD for uniformity
- *Duplicate Removal*: Removed duplicate rows to ensure unique records. 41,213 duplicates were found and removed left with 33,787 unique values out of 75,000 records that was given in the dataset. 
 
### Exploratory Data Analysis
In this phase of my analysis, i explored the dataset to meet goals such as:

- Knowing customer behaviour
- Tracking subscription types
- Identifying key trends in cancellaions and renewals

### Data Analysis
- Excel Analysis
   - *Average Subscription Duration*
     ```Excel
     =AVERAGE(I:I)
     ```
   - *Most Popular Subscription Types*
     ```Excel
     =COUNTIF(D:D,"basic")
     =COUNTIF(D:D,"premium")
     =COUNTIF(D:D,"standard")
     ```
     
- SQL Queries
   - *Total Number of Customers for each Region*
     ```SQL
     select Region,
     count(distinct customerID) as Region_Customers from Customer_Data
     group by Region
     ```

  - *Top 3 Regions with Subscription Cancellation*
    ```SQL
    select top 3 Region,
    count (*) as Top_Cancelled_Subscription_Region from Customer_Data
    where Canceled ='true'
    group by region
    ```
    
  - *Total Number of Active Subscription*
    ```SQL
    select count (*) as Active_Subscriptions from Customer_Data
    where Canceled = 'false'
    ```
  - *Total Number of Cancelled Subscription*
    ```SQL
    select count (*) as Cancelled_Subscriptions from Customer_Data
    where Canceled = 'true'
    ```

 ### Data Visualisation

 ![Customer Data- Excel](https://github.com/user-attachments/assets/1a139fd9-c78a-4296-a9f2-78cafdbfa9b5)

 ![Customer Data - Power BI](https://github.com/user-attachments/assets/d130b4f5-f0cc-4226-a3e7-58f882092909)

 ### Insights

 My analysis reveals that the Capstone Subscription Service from the 31st of January, 2022 to the 31st of August, 2023 made a total revenue of %67.5 million with a total number of 20 customers cutting across four regions( North, South, East and West). My analysis reveals that the 20 customers are shared within the four regions as we have 5 customers in each of the region. 

 The revenue analysis revealed that Basic subscription type generated the highest revenue, generating $33.8 million which is 50% of the total revenue while the Premium and Standard subscription types both generated $16.9 million each , making it 25% each of total revenue. Basic subscription type being the most popular among customers was subscribed by 10 customers from two regions (North and East) while the Premium and the standard subscription plans were both subscribed by 5 customers in South and West Region respectively.

 The average subscription duration stands at approximately 365 days, indicating a moderate level of customer commitment. I identified a high cancellation rate of 44.9% within the first 6 months of subscription; 9 customers out of 20 cancelled their subscription ( 3 customers for each subscription type), highlighting the need for enhancedcustomer support and engagement during this critical period.

 For the region by revenue analysis, all the regions did well as the revenue generated by each were close and  highly competitve. East, South, West and North regions making 25.1%, 25.0%, 25.0% and 24.9% of total revenue respectively. East region was the only region with no subscription cancellation while there were subscription cancellations in the other regions.

 ### Recommendation
 - *Diversification Strategy*

    - Offer Premium and Standard plans in North and East regions to increase Average Revenue per User (ARPU)
    - Promote Basic plan in South and West Regions to attract price-sensitive customers.

 - *Regional Specialisation*
    - Develop targeted marketing campaigns to maintain South's loyalty to Premium subscription plan even if Basic and Standard plans will be offered to the region
    - Develop targeted marketing campaigns to maintain West"s loyalty to Standard subscription plan even if Basic and Premium plans will be introduced to the region
    - Develop targeted marketing campaigns to maintain North's and East's loyalty to Basic plan even if Premium and Standard plans will be offered to the region.
 
 - *Retention and Growth*
    - Investigate cancellations reasons in North, South and West regions
    - Implement retention strategies to minimize cancellations.

 



  
  
  
