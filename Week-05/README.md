#  Healthcare Data Visualization – Week 5

##  Project Overview

This project focuses on analyzing **Healthcare Dataset** using Python. The project performs basic data exploration, data cleaning, date processing, and statistical analysis to understand patient information and healthcare records.

The analysis includes **medical conditions, patient age, gender, admission type, length of hospital stay, and billing amount**.

##  Objectives

* Load and explore healthcare data.
* Check the structure and statistical summary of the dataset.
* Identify and handle missing values.
* Process admission and discharge dates.
* Calculate the number of days patients stayed in the hospital.
* Classify admission urgency.
* Analyze billing amount statistics.
* Study patient age across medical conditions.
* Analyze gender distribution for different medical conditions.

##  Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Google Colab**

##  Dataset

The project uses the **Healthcare Dataset** stored in CSV format.

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/healthcare_dataset.csv")
```

Basic information such as the first few records, dataset shape, and statistical summary is explored using Pandas.

##  Data Processing

### 1. Data Exploration

The project checks:

* First few records
* Number of rows and columns
* Statistical summary
* Missing values

```python
print(df.head())
print(df.shape)
print(df.describe())
print(df.isnull().sum())
```

### 2. Handling Missing Values

Missing records are removed from the dataset using:

```python
df = df.dropna()
```

The `Medical Condition` column is also specifically checked and cleaned:

```python
df = df.dropna(subset=["Medical Condition"])
```

### 3. Date Processing

The **Date of Admission** and **Discharge Date** columns are converted into datetime format:

```python
df["Date of Admission"] = pd.to_datetime(df["Date of Admission"])
df["Discharge Date"] = pd.to_datetime(df["Discharge Date"])
```

### 4. Admission Urgency

Admission types are mapped into an `Urgency` column:

```python
df["Urgency"] = df["Admission Type"].map({
    "Emergency": "Emergency",
    "Urgent": "Urgent",
    "Elective": "Elective"
})
```

This helps categorize patients based on their admission type.

### 5. Hospital Stay Duration

The number of days a patient stayed in the hospital is calculated using the admission and discharge dates:

```python
df["Stay_Days"] = (
    df["Discharge Date"] - df["Date of Admission"]
).dt.days
```

##  Analysis Performed

###  Billing Statistics

The project calculates descriptive statistics for the **Billing Amount** column:

```python
df["Billing Amount"].describe()
```

This provides statistical information about healthcare billing amounts.

###  Demographic Analysis

Patient age is analyzed according to medical condition using:

```python
df.groupby("Medical Condition")["Age"].agg(["count", "mean"])
```

This provides the **number of patients and average age** for each medical condition.

###  Gender Distribution

Gender distribution across medical conditions is analyzed using a cross-tabulation:

```python
pd.crosstab(df["Medical Condition"], df["Gender"])
```

This helps understand the distribution of genders across different medical conditions.

##  Analysis Summary

| Analysis               | Purpose                                         |
| ---------------------- | ----------------------------------------------- |
| Dataset Exploration    | Understand dataset structure                    |
| Missing Value Handling | Clean incomplete records                        |
| Date Processing        | Convert dates for analysis                      |
| Urgency Classification | Categorize admission types                      |
| Stay Days              | Calculate hospital stay duration                |
| Billing Statistics     | Analyze billing amounts                         |
| Age Analysis           | Find patient count and average age by condition |
| Gender Distribution    | Analyze gender across medical conditions        |

##  How to Run

1. Open the Python file in **Google Colab**.
2. Upload `healthcare_dataset.csv`.
3. Make sure the CSV filename matches the filename used in the code.
4. Run the code step by step.
5. View the generated analysis and statistical results.

##  Project Structure

```text
Healthcare-Data-Visualization/
│
├── healthcare_data_dv_week_05.py
├── healthcare_dataset.csv
└── README.md
```

##  Conclusion

This project demonstrates how Python and Pandas can be used to **clean, process, and analyze healthcare data**. The analysis provides insights into patient demographics, medical conditions, hospital stay duration, admission urgency, gender distribution, and billing information.




