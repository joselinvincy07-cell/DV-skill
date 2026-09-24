# Superstore Sales Data Visualization

##  Project Overview

This project analyzes the **Superstore Sales Dataset** using Python. The main purpose is to explore the sales data, understand different product categories, calculate delivery days, and visualize sales patterns using graphs.

##  Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab

##  Dataset

The project uses the **Superstore Sales Dataset** in CSV format.

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/samplesuperstore.csv")
```

##  Data Analysis Performed

### 1. Load the Dataset

The CSV dataset is imported using the Pandas library.

### 2. Explore the Dataset

The following functions are used to understand the data:

```python
df.head()
df.info()
df.describe()
```

These help to view the first records, column information, and statistical summary.

### 3. Convert Date Columns

The `Order Date` and `Ship Date` columns are converted into datetime format.

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

### 4. Calculate Delivery Days

The number of days taken between ordering and shipping is calculated using:

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

### 5. Find Product Categories

Unique product categories are identified using:

```python
df['Category'].unique()
```

### 6. Check Missing Values

Missing values are checked using:

```python
df.isnull().sum()
```

### 7. Category-wise Sales Analysis

Total sales for each category are calculated using `groupby()`:

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

##  Visualizations

### Sales by Category

A bar chart is created to compare total sales between different categories.

```python
category_sales.plot(kind='bar', figsize=(8,5))
plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

### Sales Distribution

A histogram is created to understand the distribution of sales values.

```python
sns.histplot(df['Sales'], bins=30)
plt.title("Sales Distribution")
plt.show()
```

##  Project Objectives

* Understand the Superstore sales dataset.
* Perform basic data exploration.
* Handle date columns.
* Calculate delivery duration.
* Analyze category-wise sales.
* Identify missing values.
* Create meaningful data visualizations.

##  Key Analysis

The project focuses on:

* Total sales by product category
* Distribution of sales values
* Order and shipping dates
* Delivery duration
* Missing-value identification

##  How to Run

1. Open the Python notebook/script in **Google Colab** or a Python environment.
2. Upload the Superstore CSV dataset.
3. Make sure the CSV filename matches the filename used in the code.
4. Run the cells/code step by step.
5. View the generated tables and visualizations.

## Project Files

```text
Superstore-Sales-Data-Visualization/
│
├── superstore_sales_data_dv_week_1.py
├── samplesuperstore.csv
└── README.md
```

