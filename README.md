
#  UK RETAIL TRANSACTION ANALYSIS 

 Overview: This project focuses on analyzing the Online Retail dataset from the UCI Machine Learning Repository using Python. The primary goals of the project are to clean the dataset, conduct exploratory data analysis (EDA), calculate key business metrics, visualize insights, and perform advanced analytics such as customer segmentation.


##  Project Structure
The analysis is divided into the following steps:

Dataset Loading

Data Cleaning

Exploratory Data Analysis (EDA)

Key Metrics Calculation

Data Visualization




## 1. Dataset Loading
The dataset is provided as an Excel file. We load it into a pandas DataFrame to begin analysis.
## 2. Data Cleaning
To ensure the data is ready for analysis, we perform the following cleaning steps:

Remove missing customer IDs: This ensures that transactions without valid customer IDs are excluded.

Remove negative quantities: Negative values typically represent product returns, which we exclude for analysis.
## 3. Exploratory Data Analysis (EDA)
Exploratory Data Analysis is used to derive insights into customer behavior, sales performance, and product popularity.

Top-selling products: 

top_products = df.groupby('Description')['Quantity'].sum().sort_values(ascending=False).head(10)
 
Sales by country:

sales_by_country = df.groupby('Country')['Quantity'].sum().sort_values(ascending=False)

Revenue calculation:

df['Revenue'] = df['Quantity'] * df['UnitPrice']
total_revenue = df['Revenue'].sum()

## 4. Key Metrics Calculation
To provide insights into the business's financial health, we calculate several key metrics:

Total revenue per customer: Measures the total revenue generated by each customer.

Average Order Value (AOV): This metric indicates the average revenue per order, providing insight into customer purchasing behavior.
## 5. Data Visualization
Visualizations help present insights in a clear and compelling manner. We use matplotlib and seaborn to create the following charts:

Top-selling products bar chart:

import matplotlib.pyplot as plt

import seaborn as sns

plt.figure(figsize=(10,6))

sns.barplot(x=top_products.values, y=top_products.index)

plt.title('Top 10 Best Selling Products')

plt.show()

Revenue by country bar chart:

plt.figure(figsize=(10,6))

sns.barplot(x=sales_by_country.values, y=sales_by_country.index)

plt.title('Revenue by Country')

plt.show()
