import numpy as np

# 1. Load the CSV file (skip header row)
data = np.genfromtxt("supermarket_sales.csv", delimiter=",", skip_header=1)

# Display first few rows
print("First 5 records:")
print(data[:5])
print()

# 2. Extract columns
# (Change column numbers based on your dataset structure)
unit_price = data[:, 0]
quantity = data[:, 1]
total_sales = data[:, 2]
gross_income = data[:, 3]

# 3. Total Sales
overall_sales = np.sum(total_sales)
print("Total Sales:", overall_sales)

# 4. Average Transaction Value
average_transaction = np.mean(total_sales)
print("Average Transaction:", average_transaction)

# 5. High volume transactions (quantity ≥ 8)
high_volume = data[quantity >= 8]
print("\nHigh Volume Transactions:")
print(high_volume)

# 6. Statistical Analysis of Gross Income
mean_income = np.mean(gross_income)
median_income = np.median(gross_income)
variance_income = np.var(gross_income)
std_income = np.std(gross_income)

print("\nGross Income Statistics")
print("Mean:", mean_income)
print("Median:", median_income)
print("Variance:", variance_income)
print("Standard Deviation:", std_income)

# 7. Vectorized Revenue Calculation
revenue = quantity * unit_price
print("\nCalculated Revenue (first 5):")
print(revenue[:5])

# 8. Insight Example
print("\nInsights:")
print("Average sales per transaction is", round(average_transaction,2))
print("Total overall sales recorded:", overall_sales)
print("Higher standard deviation indicates variation in income.")
