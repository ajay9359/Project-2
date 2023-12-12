# Customer Report ABC Bank -Dashboard

## Problem Statement

This dashboard facilitates a comprehensive understanding of customer demographics and financial performance for ABC Bank. By leveraging calculated measures, visualizations, and advanced analytics, the objective is to provide actionable insights and strategic directions based on the bank's data.


### Steps followed 
- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values
- Step 5 : Create calculated measures for various KPIs in the dataset. Examples include:
Number of Customers
Revenue
Forecast
Average Age
Average Balance
Average Credit Limit

            Revenue = IF('500000 CC Records New'[Expiry Date] < TODAY(),DATEDIFF('500000 CC Records New'[Issue Date],'500000 CC Records New'[Expiry Date],MONTH),DATEDIFF('500000 CC Records New'[Issue Date],TODAY(),MONTH))*10
            Forcast = IF('500000 CC Records New'[Expiry Date]>TODAY(),DATEDIFF(TODAY(),'500000 CC Records New'[Expiry Date],MONTH),BLANK())*10
            AverageBalanceByAgeGroup = CALCULATE(AVERAGE('P6-UK-Bank-Customers'[Balance]),'P6-UK-Bank-Customers'[Balance] > 50000,ALLEXCEPT('P6-UK-Bank-Customers', 'P6-UK-Bank-Customers'[Age  range]))
            Average Age = AVERAGE('P6-UK-Bank-Customers'[Age])
            Average Balance = AVERAGE('P6-UK-Bank-Customers'[Balance])

![Screenshot (297)](https://github.com/ajay9359/Project-2/assets/153490133/9643ac55-de4f-4711-96bf-a40197976cd5)

- Step 6 : Implement slicers for filtering the data. Slicers can include:
Region
Job Classification
Gender
Quarter
Balance

![Screenshot (298)](https://github.com/ajay9359/Project-2/assets/153490133/5a8f5e05-374e-4ec7-9c0e-94e6925e396c)

- Step 7: Create various visualizations to represent the data, including:
Pie chart for customer distribution by region
Stacked column chart showing customers quarter-wise
Stacked column chart showing balance distribution by job classification, gender-wise
Stacked bar chart showing age range versus average balance, gender-wise
Stacked area chart showing balance month-wise, gender-wise
Additional Visualizations:

- Step 8: Implement a table visualization showcasing the top 2 customers with the highest balances.
Report Layout:
- Step 9: Organize the visuals on the report canvas, arranging them logically and aesthetically.
Review and Refinement:
- Step 10: Review the report, ensuring that all visualizations and slicers are working as expected.
Refine formatting options, colors, and other design elements for a professional look.
- Step 12 : Make Calculated Measures for various Conditions
![Screenshot (299)](https://github.com/ajay9359/Project-2/assets/153490133/8662a08f-3fae-40a4-8ac0-e62be80c3654)

- Step 11 : The report was then published to Power BI Service.
 
 
![Publish_Message](https://github.com/ajay9359/Project-2/assets/153490133/9a1b2c79-036f-4a00-9c30-987ffa1a9480)
)



 
 # Report Snapshot (Power BI DESKTOP)

 
![image](https://github.com/ajay9359/Project-2/assets/153490133/2b9fbb85-4725-4700-adb3-9d513638f41b)

![image](https://github.com/ajay9359/Project-2/assets/153490133/72eeab6f-47c7-4606-99cc-75a4dc3f7014)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the report;

The age distribution is varied, ranging from 18 to 63 years.
There's a significant presence of customers in the 30-40 age range, indicating a potentially financially active demographic.

Customer Distribution by Region:
England has the highest concentration of customers, followed by Scotland, Wales, and Northern Ireland.
This could indicate where the bank has a stronger market presence or where there is a higher population density.
