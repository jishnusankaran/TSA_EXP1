# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 21/11/2026

# AIM:
To develop a Python program to plot the time series data using the New Car Sales dataset and visualize the changes in the total number of cars sold over time.
### Dataset Name : New Car Sales by Make
# ALGORITHM:
1.Import the required packages such as Pandas and Matplotlib.
2.Read the New Car Sales dataset using Pandas.
3.Convert the Year and Month columns into datetime format.
4.Group the data by month and calculate the total quantity of cars sold.
5.Plot the time series data using a line graph.
6.Add a suitable title, X-axis label, Y-axis label and grid.
7.Display the graph.

# PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('/content/New Car Sales by Make.csv')

df['Date'] = pd.to_datetime(dict(
    year=df['Year'],
    month=df['Month'],
    day=1
))

monthly_sales = df.groupby('Date')['Quantity'].sum()

plt.figure(figsize=(10, 5))

plt.plot(monthly_sales.index, monthly_sales.values,
         color='blue', linewidth=1.8)

plt.title('New Car Sales Over Time')
plt.xlabel('Year')
plt.ylabel('Number of Cars Sold')

plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()
```


# OUTPUT:
<img width="813" height="398" alt="Screenshot 2026-11-21 083641" src="https://github.com/user-attachments/assets/e94f48e2-e8ec-4970-b915-e70b6dc52953" />



# RESULT:
Thus, we have successfully created and executed a Python program to plot the time series data using the New Car Sales dataset. The graph clearly represents the changes in the total number of cars sold from January 2007 to January 2017.
