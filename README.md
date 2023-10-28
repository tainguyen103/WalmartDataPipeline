# Project: Build a Walmart sales database

Walmart is the biggest retail store in the United States. Just like others, they have been expanding their e-commerce part of the business. By the end of 2022, e-commerce represented a roaring $80 billion in sales, which is 13% of total sales of Walmart. One of the main factors that affects their sales is public holidays, like the Super Bowl, Labour Day, Thanksgiving, and Christmas. 

## 1. Objective: we will create a data pipeline for the analysis of demand and supply around the holidays and running preliminary analysis of the data. 

## 2. Project breakdown:

We will be working with two data sources: grocery sales (from PostgreSQL database) and complementary data (which is the `extra_data.parquet` file). 

- Here is information about all the available columns in the two data files:
  - `"index"` - unique ID of the row
  - `"Store_ID"` - the store number
  - `"Date"` - the week of sales
  - `"Weekly_Sales"` - sales for the given store
  - `"IsHoliday"` - Whether the week contains a public holiday - 1 if yes, 0 if no.
  - `"Temperature"` - Temperature on the day of sale
  - `"Fuel_Price"` - Cost of fuel in the region
  - `"CPI"` – Prevailing consumer price index
  - `"Unemployment"` - The prevailing unemployment rate
  - `"MarkDown1"`, `"MarkDown2"`, `"MarkDown3"`, `"MarkDown4"` - number of promotional markdowns
  - `"Dept"` - Department Number in each store
  - `"Size"` - size of the store
  - `"Type"` - type of the store (depends on `Size` column)


- We will need to merge those files for further data manipulations and store the merged file in the `clean_data.csv` file that should contain the following columns:
  - `"Store_ID"`
  - `"Month"`
  - `"Dept"`
  - `"IsHoliday"`
  - `"Weekly_Sales"`
  - `"CPI"`
  - "`"Unemployment"`"

After merging and cleaning the data, we will analyze monthly sales of Walmart and store the results of analysis in the `agg_date.csv` file that should look like:

|  Month | Weekly_Sales  | 
|---|---|
| 1.0  |  33174.178494 |
|  2.0 |  34333.326579 |
|  ... | ...  |  
