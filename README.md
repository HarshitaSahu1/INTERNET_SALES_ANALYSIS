# INTERNET_SALES_ANALYSIS
This project analyzes internet sales performance across multiple dimensions such as product categories, customer segments, regions, and time periods. The goal is to derive insights into sales trends, high-performing products, customer behavior, and potential areas of improvement in online sales strategies.


## 🛠 Tools Used

- SQL (for data querying and cleaning)
- Power BI (for dashboards and data visualization)
- Notepad (to save SQL scripts)

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
