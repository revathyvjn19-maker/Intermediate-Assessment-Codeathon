# Intermediate-Assessment-Codeathon
Power BI – Module End Evaluation
# Q1: Data Cleaning and Loading
Imported the dataset into Power BI using Power Query Editor.

i) Handling Missing Values

Identified missing values in Order Date, Customer  Name, Region, Product, Unit Price, Sales, Cost and Profit columns

•	Order Date: Removed rows containing missing dates using the Remove Empty option.

•	Customer Name, Region and Product: Replaced missing values with "Unknown".

•	Unit Price, Sales, Cost and Profit: Added custom columns to calculate and replace missing values 

Unit Price = Sales / Quantity

Sales = Quantity * Unit Price 

Cost = Sales – Profit 

Profit = Sales - Cost
