# Credit Card Financial Dashboard – Power BI

This project presents an interactive Credit Card Financial Dashboard created using Power BI to analyze transaction data, revenue trends, customer spending behavior, and key financial KPIs.

#Key Features
- Total revenue
- Total Interest
- Total Transactions amount
- Total Transactions Count
- Avg Css


# Tools & Technologies
- Power BI
- CSV (Data Source)/ mysql

#Files Included
- Power BI Dashboard (.pbix)
- Dataset files
- Screenshots of dashboard

#Use Case
This dashboard helps financial institutions understand credit card usage patterns and make data-driven business decisions.

#Project Type
Self-Learning / Portfolio Project /Academic Project  
This dashboard was created independently as part of self-learning, with guidance from an online YouTube tutorial.


#Dax measures
Age Grooup = SWITCH(
    TRUE(),
    'cc_db cust_detail'[Customer_Age]<30,"20-30",
    'cc_db cust_detail'[Customer_Age]>=30 && 'cc_db cust_detail'[Customer_Age]<40,"30-40",
    'cc_db cust_detail'[Customer_Age]>=40 && 'cc_db cust_detail'[Customer_Age]<50,"40-50",
    'cc_db cust_detail'[Customer_Age]>=50 && 'cc_db cust_detail'[Customer_Age] <60 ,"50-60",
    'cc_db cust_detail'[Customer_Age]>=60,"60+",
    "Unknown"
)


IncomeGroup = SWITCH(
    TRUE(),
    'cc_db cust_detail'[Income] < 35000,"Low",
    'cc_db cust_detail'[Income] >= 35000 && 'cc_db cust_detail'[Income]<=70000,"Mid",
    'cc_db cust_detail'[Income] > 70000,"High",
    "Unknown"
)

Revenue = 'cc_db cc_details'[Annual_Fees]+ 'cc_db cc_details'[Total_Trans_Amt] +'cc_db cc_details'[Interest_Earned]


