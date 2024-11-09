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


  
  
  
