# Superstore Sales Data Visualization – Week 2

##  Project Overview

This project focuses on analyzing the **Superstore Sales Dataset** using Python and different data visualization techniques.

The project explores sales, profit, categories, discounts, and relationships between numerical variables using different types of graphs.

##  Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab

##  Dataset

The project uses the **Superstore Sales Dataset** in CSV format.

The dataset is loaded using Pandas and basic information about the data is explored using `head()`, `info()`, and `describe()`.

##  Data Preparation

The `Order Date` and `Ship Date` columns are converted into datetime format. Delivery days are then calculated by finding the difference between the shipping date and order date.

Missing values and unique product categories are also checked during the analysis.

##  Visualizations

### 1. Bar Plot

Bar plots are used to compare **sales and profit across categories**.

Example visualizations include:

* Profit by Category
* Sales Distribution by Category

The main purpose is to compare values between different categories.

### 2. Box Plot

Box plots are used to understand:

* Data distribution
* Median value
* Outliers
* Variation

The project creates:

* Profit Distribution
* Profit Variation Across Categories

### 3. Discount vs Profit Analysis

A scatter plot is used to analyze the relationship between **Discount and Profit**.

The purpose is to understand whether discounts improve sales or affect profitability and to identify discount levels where profit may start decreasing.

### 4. Correlation Heatmap

A correlation heatmap is created to understand the relationship between numerical variables.

The numerical columns are selected and their correlation values are calculated using:

```python
corr = numeric_df.corr()
```

The correlation values are then displayed using a heatmap.

##  Project Objectives

* Analyze Superstore sales data.
* Compare sales and profit across categories.
* Understand profit distribution and variation.
* Study the relationship between discount and profit.
* Identify outliers using box plots.
* Analyze relationships between numerical variables using correlation.
* Create meaningful visualizations using Seaborn and Matplotlib.

##  Visualizations Included

| Visualization       | Purpose                                              |
| ------------------- | ---------------------------------------------------- |
| Bar Plot            | Compare sales and profit                             |
| Box Plot            | Analyze distribution, median, outliers and variation |
| Scatter Plot        | Study Discount vs Profit                             |
| Correlation Heatmap | Understand relationships between numerical variables |

##  How to Run

1. Open the Python file in **Google Colab**.
2. Upload the Superstore CSV dataset.
3. Make sure the CSV filename matches the filename used in the code.
4. Run the code cells step by step.
5. View the generated graphs and analysis.

##  Project Files

```text
Superstore-Sales-Data-Visualization-Week-2/
│
├── superstore_sales_data_dv_week_2.py
├── samplesuperstore.csv
└── README.md
```


BCA Student

