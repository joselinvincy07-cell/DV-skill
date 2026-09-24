# Apple Stock Data Visualization – Week 3

##  Project Overview

This project focuses on analyzing **Apple Stock Data** using Python and Pandas.

The project demonstrates basic data loading, data cleaning, data exploration, date conversion, and sorting of historical stock data.

##  Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Google Colab

##  Dataset

The project uses historical **Apple (AAPL) stock data**.

The data is loaded and analyzed using Pandas. The project works with both CSV and Excel data formats.

##  Data Analysis and Preparation

### 1. Load CSV Data

The Apple stock data is initially loaded from a CSV file using:

```python
df = pd.read_csv("/content/AAPL.csv")
```

The first few records and dataset information are displayed to understand the data.

### 2. Data Cleaning

Missing values and duplicate records are removed using:

```python
df = df.dropna()
df = df.drop_duplicates()
```

This helps to improve the quality of the dataset before analysis.

### 3. Load Excel Data

The project also demonstrates loading Apple stock data from an Excel file:

```python
df = pd.read_excel("/content/AAPL.excel.xlsx")
```

The first and last records are displayed using `head()` and `tail()`.

### 4. Explore Dataset Columns and Data Types

The project checks:

* Column names
* Data types
* Statistical summary

The following functions are used:

```python
df.columns
df.dtypes
df.describe()
```

### 5. Handle Missing Values

Missing values are removed from the dataset using:

```python
df = df.dropna()
```

### 6. Convert Date Column

The `Date` column is converted into datetime format:

```python
df["Date"] = pd.to_datetime(df["Date"])
```

This makes the date column suitable for time-based analysis.

### 7. Sort Data by Date

The stock data is sorted according to the `Date` column:

```python
df = df.sort_values("Date")
```

This arranges the historical stock records in date order.

##  Project Objectives

* Load Apple stock data using Python.
* Work with CSV and Excel datasets.
* Explore the structure of the dataset.
* Remove missing values.
* Remove duplicate records.
* Check columns and data types.
* Generate statistical summaries.
* Convert dates into datetime format.
* Sort historical stock data by date.

##  Data Processing Techniques

| Technique           | Purpose                      |
| ------------------- | ---------------------------- |
| `read_csv()`        | Load CSV data                |
| `read_excel()`      | Load Excel data              |
| `head()`            | View first records           |
| `tail()`            | View last records            |
| `info()`            | Check dataset information    |
| `dtypes`            | Check data types             |
| `describe()`        | Generate statistical summary |
| `dropna()`          | Remove missing values        |
| `drop_duplicates()` | Remove duplicate records     |
| `to_datetime()`     | Convert date values          |
| `sort_values()`     | Sort data by date            |

##  How to Run

1. Open the Python file in **Google Colab**.
2. Upload the required Apple stock dataset.
3. Make sure the file names match the names used in the code.
4. Run the code step by step.
5. Check the displayed data and dataset information.

##  Project Files

```text
Apple-Stock-Data-Visualization-Week-3/
│
├── apple_stock_data_dv_week_3.py
├── Apple_historical_data.csv
└── README.md
```



BCA Student

