# Credit-card-Financial-Dashboard
Excited to share my latest Power BI project – a Credit Card Dashboard that provides deep insights into customer spending habits, transaction trends, and fraud detection.

🔹 Key Insights from the Dashboard:

✅ Transaction Analytics – Analyzed total spending, transaction volume, and top payment modes.

✅ Customer Segmentation – Grouped customers into high, medium, and low spenders to understand behavior patterns.

✅ Spending Trends – Identified monthly and seasonal spending fluctuations to predict future trends.

✅ Fraud Detection – Flagged unusual transactions to enhance security measures.

✅ Top Merchants & Locations – Mapped where and how customers spend the most.

💡 Key Takeaways:

📊 Data visualization helps businesses make informed decisions and improve financial strategies.

🔍 Identifying customer spending patterns enables banks to offer personalized rewards & credit limits.

⚠️ Fraud detection is critical to ensure secure transactions in the digital economy.

Dax Queries Used:

1. current_week_revenue = CALCULATE(

    SUM(credit_card[Revenue]),

    FILTER(

        ALL(credit_card),

        credit_card[Week_num2]=MAX(credit_card[Week_num2]

    )))

2. previous_week_revenue = CALCULATE(

    SUM(credit_card[Revenue]),

    FILTER(

        ALL(credit_card),

        credit_card[Week_num2]=(MAX(credit_card[Week_num2]

    )-1)))

3. Revenue = credit_card[Total_Trans_Amt] + credit_card[Interest_Earned] + credit_card[Annual_Fees]

4. Week_num2 = WEEKNUM(credit_card[Week_Start_Date].[Date])

5. Week on Week revenue = DIVIDE([current_week_revenue]-[previous_week_revenue],[previous_week_revenue])

6. Age_Group = SWITCH(

    TRUE(),

    customer[Customer_Age]<=30,"20-30",

    customer[Customer_Age]>=30 && customer[Customer_Age]<40,"30-40",

    customer[Customer_Age]>=40 && customer[Customer_Age]<50,"40-50",

    customer[Customer_Age]>=50 && customer[Customer_Age]<60,"50-60",

    customer[Customer_Age]>=60,"60+",

    "unknown"

    )

7. Income_Group = SWITCH(

TRUE(),

customer[Income]<35000,"Low",

customer[Income]>=35000 && customer[Income]<75000,"Middle",

customer[Income]>=75000,"High",

"unknown") 
