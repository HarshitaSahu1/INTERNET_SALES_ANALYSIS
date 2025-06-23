# INTERNET_SALES_ANALYSIS
This project analyzes internet sales performance across multiple dimensions such as product categories, customer segments, regions, and time periods. The goal is to derive insights into sales trends, high-performing products, customer behavior, and potential areas of improvement in online sales strategies.


## 🛠 Tools Used

- SQL (for data querying and cleaning)
- Power BI (for dashboards and data visualization)
- Notepad (to save SQL scripts)
- 
## 📂 Raw Data Files

The following raw datasets were used for analysis:
DIM_CALENDAR.csv - It contains all the dates of transaction 
DIM_Customer.csv - It contains all the demographics of a customers it city..
DIM_Product.csv - It cotains all the realted data of a product its categories,sub_categories,product_status and many_more 
FACT_InternetSales - It contains all the data related to sales 

All files are available in the project folder and were used in SQL queries and Power BI dashboards.

## 🔍 Key SQL Queries

- 📦 Sales by Product Line and Product Status
- 🧾 Current vs Outdated Products Performance
- 🚻 Gender-wise Purchase Behavior

- #### 🧪 Sample SQL Query
- --- categorization of customer as loyal and likely chur customers 
select customerkey, datediff(day,datefirstpurchase,max(orderdatekey))as dates_diff , 
case when datediff(day,datefirstpurchase,max(orderdatekey))<7 then 'Likely_Churn'
when datediff(day,datefirstpurchase,max(orderdatekey))>30 then 'Loyal_Customers'
else 'Moderate'
end  as 'Customer_Categorization'
from combine_table
group by CustomerKey,DateFirstPurchase
