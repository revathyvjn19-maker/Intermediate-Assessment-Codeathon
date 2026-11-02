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

 **if [UnitPrice]=null then [Sales]/[Quantity] else [UnitPrice]**

Sales = Quantity * Unit Price 

**if [Sales]=null then [Unit Price 1]*[Quantity] else [Sales]**

Cost = Sales – Profit 

**if [Cost]=null then [Sales 2]-[Profit] else [Cost]**

Profit = Sales - Cost

**if [Profit]=null then [Sales 2]-[Cost 1] else [Profit]**

ii) Removing Duplicate Rows

•	Selected the dataset in Power Query Editor and Removed duplicate rows from the dataset

Home → Remove Rows → Remove Duplicates.

iii) Standardizing the Order Date Column

•	Changed the data type of the Order Date column to Date.

•	Standardized the date format to DD-MM-YYYY.

iv) Loading the Cleaned Dataset

•	Home → Close & Apply.

•	Loaded the cleaned dataset into the Power BI data model.

# Q2: Visualizations and Insights

a) Pie Chart – Order Distribution Across Regions

Created a Pie Chart to analyse the distribution of orders across different regions.

•	Legend: Region

•	Values: Count of Order ID

b) Column Chart – Top 5 Trending Products

Created a Clustered Column Chart to identify the top 5 products based on the number of times they were ordered.

•	X-axis: Product

•	Y-axis: Count of Order ID

Applied Top N Filter:

-	Opened the Filters
   
-	Selected the Product field.

-	Changed the filter type to Top N.

-	Selected Top 5 under Show Items.

-	Added Count of Order ID to the By Value field.

-	Clicked Apply Filter.

c) Line Chart – Profit Trend Over Time
Created a Line Chart to analyse the profit trend over time.

•	X-axis: Order Date

•	Y-axis: Sum of Profit

# Q3: DAX Calculations

a) Calculated Table – East Region Orders

Created a calculated table named East Region Orders to display only orders from the East region.

East Region Orders = FILTER('Sales Data','Sales Data'[Region]="East")

b) Calculated Column – Profit Cost Difference

Created a calculated column named Profit Cost Difference to calculate the difference between Profit and Cost.

Profit Cost Difference = Profit Cost Difference = 'Sales Data'[Calculated Cost]-'Sales Data'[Calculated Profit]

c) Measure – Total Profit

Created a measure named Total Profit to calculate the total profit earned from all orders.

Total Profit = Total Profit = SUM('Sales Data'[Calculated Profit])
