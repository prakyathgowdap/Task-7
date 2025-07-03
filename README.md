Task 7: Basic Sales Summary Using SQLite and Python
Objective
To analyze sales data by loading it into a SQLite database and using SQL inside Python to summarize total quantity sold and revenue per product. The result is displayed using print() and visualized with a bar chart using matplotlib.

Tools Used
Python (Juypeter Notebook)
pandas
sqlite3 (built-in)
matplotlib
What I Did
Downloaded sales_data_sample.csv from Hugging Face.
Handled encoding errors while loading the CSV using encoding='ISO-8859-1'.
Selected required columns: PRODUCTLINE, QUANTITYORDERED, PRICEEACH.
Renamed them to: product, quantity, and price.
Created a SQLite database (sales_data.db) using sqlite3 and loaded the cleaned data into a table called sales.
Ran a SQL query to:
Group records by product
Sum up quantity and quantity * price for revenue
Printed the summary results using pandas.DataFrame.
Plotted revenue by product using a simple bar chart.
Saved the chart as sales_chart.png.
SQL Query Used
SELECT product,
       SUM(quantity) AS total_qty,
       ROUND(SUM(quantity * price), 2) AS revenue
FROM sales
GROUP BY product
