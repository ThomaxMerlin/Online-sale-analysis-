Online Sales Data Analysis
With Jupyter Notebook

This Jupyter Notebook demonstrates how to analyze online sales data using Python libraries like pandas, matplotlib, and seaborn. The dataset contains information about transactions, including product details, units sold, revenue, region, and payment methods. The analysis includes calculating total revenue, identifying best-selling products, and visualizing sales trends by region, product category, and payment method.

Table of Contents
Prerequisites

Getting Started

Running the Code

Code Explanation

Results

License

Prerequisites
Before running the code, ensure you have the following installed:

Python 3.x

Required Python libraries:

bash
Copy
pip install pandas matplotlib seaborn jupyter
Jupyter Notebook (to run the .ipynb file).

Getting Started
Download the Dataset
Ensure the dataset Online Sales Data.csv is in the same directory as the notebook.

Launch Jupyter Notebook
Start Jupyter Notebook:

bash
Copy
jupyter notebook
Open the .ipynb file from the Jupyter Notebook interface.

Running the Code
Open the .ipynb file in Jupyter Notebook.

Run each cell sequentially to execute the code.

Code Explanation
1. Import Libraries
python
Copy
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
Libraries used for data manipulation and visualization.

2. Load and Explore Data
python
Copy
data = pd.read_csv('Online Sales Data.csv')
print(data.head())
print(data.info())
Load the dataset and explore its structure.

3. Calculate Total Revenue
python
Copy
total_revenue = data['Total Revenue'].sum()
print(f"Total Revenue: ${total_revenue:.2f}")
Calculate the total revenue generated from all transactions.

4. Identify Best-Selling Product
python
Copy
best_selling_product = data.loc[data['Units Sold'].idxmax()]
print(f"Best Selling Product: {best_selling_product['Product Name']} with {best_selling_product['Units Sold']} units sold")
Identify the product with the highest number of units sold.

5. Analyze Sales by Region
python
Copy
sales_by_region = data.groupby('Region')['Total Revenue'].sum().reset_index()
plt.figure(figsize=(10, 6))
sns.barplot(x='Region', y='Total Revenue', data=sales_by_region, palette='viridis')
plt.title('Total Revenue by Region')
plt.xlabel('Region')
plt.ylabel('Total Revenue ($)')
plt.show()
Visualize total revenue by region using a bar plot.

6. Analyze Sales by Product Category
python
Copy
sales_by_category = data.groupby('Product Category')['Total Revenue'].sum().reset_index()
plt.figure(figsize=(10, 6))
sns.barplot(x='Product Category', y='Total Revenue', data=sales_by_category, palette='magma')
plt.title('Total Revenue by Product Category')
plt.xlabel('Product Category')
plt.ylabel('Total Revenue ($)')
plt.show()
Visualize total revenue by product category using a bar plot.

7. Analyze Sales by Payment Method
python
Copy
sales_by_payment = data.groupby('Payment Method')['Total Revenue'].sum().reset_index()
plt.figure(figsize=(8, 6))
sns.barplot(x='Payment Method', y='Total Revenue', data=sales_by_payment, palette='plasma')
plt.title('Total Revenue by Payment Method')
plt.xlabel('Payment Method')
plt.ylabel('Total Revenue ($)')
plt.show()
Visualize total revenue by payment method using a bar plot.

8. Identify Most Expensive Product
python
Copy
most_expensive_product = data.loc[data['Unit Price'].idxmax()]
print(f"Most Expensive Product Sold: {most_expensive_product['Product Name']} at ${most_expensive_product['Unit Price']:.2f}")
Identify the most expensive product sold.

9. Analyze Average Unit Price by Product Category
python
Copy
avg_price_by_category = data.groupby('Product Category')['Unit Price'].mean().reset_index()
plt.figure(figsize=(10, 6))
sns.barplot(x='Product Category', y='Unit Price', data=avg_price_by_category, palette='coolwarm')
plt.title('Average Unit Price by Product Category')
plt.xlabel('Product Category')
plt.ylabel('Average Unit Price ($)')
plt.xticks(rotation=45)
plt.show()
Visualize the average unit price by product category using a bar plot.

10. Analyze Total Units Sold by Product Category
python
Copy
total_units_sold_by_category = data.groupby('Product Category')['Units Sold'].sum().reset_index()
plt.figure(figsize=(10, 6))
sns.barplot(x='Product Category', y='Units Sold', data=total_units_sold_by_category, palette='rocket')
plt.title('Total Units Sold by Product Category')
plt.xlabel('Product Category')
plt.ylabel('Total Units Sold')
plt.xticks(rotation=50)
plt.show()
Visualize the total units sold by product category using a bar plot.

11. Identify Top 5 Products by Revenue
python
Copy
top_5_products_by_revenue = data.groupby('Product Name')['Total Revenue'].sum().nlargest(5).reset_index()
plt.figure(figsize=(10, 6))
sns.barplot(x='Product Name', y='Total Revenue', data=top_5_products_by_revenue, palette='flare')
plt.title('Top 5 Products by Revenue')
plt.xlabel('Product Name')
plt.ylabel('Total Revenue ($)')
plt.xticks(rotation=45)
plt.show()
Visualize the top 5 products by revenue using a bar plot.

Results
Total Revenue: The total revenue generated from all transactions.

Best-Selling Product: The product with the highest number of units sold.

Sales by Region: A bar plot showing total revenue by region.

Sales by Product Category: A bar plot showing total revenue by product category.

Sales by Payment Method: A bar plot showing total revenue by payment method.

Most Expensive Product: The product with the highest unit price.

Average Unit Price by Category: A bar plot showing the average unit price by product category.

Total Units Sold by Category: A bar plot showing the total units sold by product category.

Top 5 Products by Revenue: A bar plot showing the top 5 products by revenue.

License
This project is open-source and available under the MIT License. Feel free to use, modify, and distribute it as needed.

Support
If you encounter any issues or have questions, feel free to open an issue in this repository or contact me at your-email@example.com.

Enjoy exploring online sales data analysis with Jupyter Notebook! 
