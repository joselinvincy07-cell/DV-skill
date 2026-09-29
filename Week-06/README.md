#  Healthcare Data Visualization – Week 6

##  Project Overview

This project focuses on analyzing and visualizing **Healthcare Data** using Python.

The project explores the relationship between **Medical Conditions, Insurance Providers, and Billing Amounts** using different data visualization techniques.

The main visualizations used in this project are **Stacked Bar Charts and Violin Plots**.

##  Objectives

* Load and explore the healthcare dataset.
* Analyze billing amounts based on medical conditions.
* Compare billing amounts across insurance providers.
* Visualize the distribution of billing amounts.
* Understand billing variations between medical conditions.
* Analyze billing amount distribution across insurance providers.

##  Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Google Colab**

##  Dataset

The project uses a healthcare dataset stored in CSV format.

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/healthcare_dataset.csv")
```

The first few records are displayed using `df.head()` to understand the dataset.

##  Data Analysis

### 1. Billing Amount by Medical Condition and Insurance Provider

The project groups the data by:

* Medical Condition
* Insurance Provider
* Billing Amount

The total billing amount is calculated using:

```python
billing_data = df.groupby(
    ['Medical Condition', 'Insurance Provider']
)['Billing Amount'].sum().unstack(fill_value=0)
```

### 2. Stacked Bar Chart

A **stacked bar chart** is created to compare the total billing amount for different medical conditions and insurance providers.

```python
billing_data.plot(
    kind='bar',
    stacked=True,
    figsize=(12, 6)
)
```

This visualization helps compare the contribution of different insurance providers to the total billing amount for each medical condition.

### 3. Billing Amount by Medical Condition

A **violin plot** is used to visualize the distribution of billing amounts across different medical conditions.

```python
sns.violinplot(
    data=df,
    x='Medical Condition',
    y='Billing Amount'
)
```

The chart shows how billing amounts are distributed for each medical condition.

### 4. Billing Amount Distribution by Medical Condition

The project also displays a visualization titled **Billing Amount Distribution by Medical Condition**, with medical conditions on the X-axis and billing amount on the Y-axis.

### 5. Billing Amount Distribution by Insurance Provider

Another violin plot is created to analyze billing amount distribution across different insurance providers.

```python
sns.violinplot(
    data=df,
    x='Insurance Provider',
    y='Billing Amount'
)
```

This helps visualize the variation and distribution of billing amounts for each insurance provider.

##  Visualizations Used

| Visualization     | Purpose                                                                   |
| ----------------- | ------------------------------------------------------------------------- |
| Stacked Bar Chart | Compare total billing amounts by medical condition and insurance provider |
| Violin Plot       | Analyze billing amount distribution by medical condition                  |
| Violin Plot       | Analyze billing amount distribution by insurance provider                 |

##  Key Analysis Areas

The project analyzes:

* **Medical Condition**
* **Insurance Provider**
* **Billing Amount**
* **Total Billing Amount**
* **Billing Amount Distribution**

##  How to Run

1. Open the Python file in **Google Colab** or a Python environment.
2. Upload the `healthcare_dataset.csv` file.
3. Make sure the dataset filename matches the filename used in the code.
4. Run the code step by step.
5. View the generated charts and visualizations.

##  Project Structure

```text
Healthcare-Data-Visualization-Week-6/
│
├── health_care_data_week_06.py
├── healthcare_dataset.csv
└── README.md
```

##  Conclusion

This project demonstrates how **Python, Pandas, Matplotlib, and Seaborn** can be used to analyze and visualize healthcare billing data.

The visualizations provide a clear way to examine billing amounts across **medical conditions and insurance providers**, making the dataset easier to understand through graphical representation.


