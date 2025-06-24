# Walmart-Sales

🔍 Step 1: Understand the Dataset
Let’s first inspect the structure of the CSV file to see what columns are available for querying.

I'll now load and display the first few rows of your data.

The dataset has the following columns:

Store – Store number

Date – Week-ending date (dd-mm-yyyy)

Weekly_Sales – Total sales for the week

Holiday_Flag – 1 if the week includes a public holiday, else 0

Temperature – Average temperature that week

Fuel_Price – Cost of fuel in the area

CPI – Consumer Price Index

Unemployment – Unemployment rate

 Example 1: SELECT & WHERE

 import pandas as pd

# Load the Walmart Sales CSV file
file_path = "/mnt/data/Walmart_Sales.csv"
df = pd.read_csv(file_path)

# Display the first 5 rows and the column names
df.head(), df.columns.tolist()

Result

(   Store        Date  Weekly_Sales  Holiday_Flag  Temperature  Fuel_Price  \
 0      1  05-02-2010    1643690.90             0        42.31       2.572   
 1      1  12-02-2010    1641957.44             1        38.51       2.548   
 2      1  19-02-2010    1611968.17             0        39.93       2.514   
 3      1  26-02-2010    1409727.59             0        46.63       2.561   
 4      1  05-03-2010    1554806.68             0        46.50       2.625   
 
           CPI  Unemployment  
 0  211.096358         8.106  
 1  211.242170         8.106  
 2  211.289143         8.106  
 3  211.319643         8.106  
 4  211.350143         8.106  ,
 ['Store',
  'Date',
  'Weekly_Sales',
  'Holiday_Flag',
  'Temperature',
  'Fuel_Price',
  'CPI',
  'Unemployment'])

  Example 2: ORDER BY

  # Filter for rows where Holiday_Flag == 1 (i.e., holiday weeks)
holiday_sales = df[df['Holiday_Flag'] == 1][['Store', 'Weekly_Sales']]

# Display the first 5 rows
holiday_sales.head()

Result
    Store  Weekly_Sales
1       1    1641957.44
31      1    1507460.69
42      1    1955624.11
47      1    1367320.01
53      1    1649614.93

