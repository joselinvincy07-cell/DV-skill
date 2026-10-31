#  House Sales Data Analysis – Week 09

##  Project Overview

This project focuses on analyzing and cleaning the **House Sales Dataset** using Python. It involves data exploration, data preprocessing, feature engineering, outlier detection, and statistical analysis.

The project analyzes house prices, property sizes, construction years, renovation details, and sales dates to prepare a clean dataset for further analysis.

##  Project Objectives

- Explore and understand the house sales dataset.
- Identify missing values and duplicate records.
- Convert date columns into datetime format.
- Extract year, month, and day from sales dates.
- Clean and process numerical columns.
- Calculate property age and renovation details.
- Calculate price per square foot.
- Detect house price outliers using the IQR method.
- Generate a cleaned dataset for further analysis.

##  Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab

##  Dataset

The project uses the **King County House Sales Dataset** in CSV format.

**Dataset File:** `kc_house_data.csv`

The dataset contains information about house prices, bedrooms, bathrooms, living area, lot size, construction year, renovation year, and sales dates.

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/kc_house_data.csv")
```

##  Data Exploration

The dataset is explored using the following functions:

```python
df.head()
df.tail()
df.info()
df.describe()
df.shape
df.columns
```

These functions help understand the dataset structure, records, columns, and statistical information.

Missing values and duplicate records are also identified using:

```python
df.isnull().sum()
df.duplicated().sum()
```

## 🧹 Data Cleaning and Preprocessing

### 1. Date Conversion

The sales date column is converted into datetime format.

```python
df["date"] = pd.to_datetime(
    df["date"].astype(str).str[:8],
    format="%Y%m%d",
    errors="coerce"
)
```

### 2. Extract Date Information

The year, month, and day are extracted from the sales date.

```python
df["sale_year"] = df["date"].dt.year
df["sale_month"] = df["date"].dt.month
df["sale_day"] = df["date"].dt.day
```

### 3. Remove Duplicate Records

Duplicate records are removed using:

```python
df.drop_duplicates(inplace=True)
```

### 4. Numerical Data Conversion

Important numerical columns are converted into numeric format.

- Price
- Bedrooms
- Bathrooms
- Square Feet of Living Area
- Square Feet of Lot Area
- Year Built
- Year Renovated

```python
for col in numeric_cols:
    df[col] = pd.to_numeric(df[col], errors="coerce")
```

### 5. Handle Missing and Invalid Values

Rows with missing essential values are removed. Invalid records with non-positive house prices, living area, or lot area are also filtered out.

##  Feature Engineering

New columns are created to support further house sales analysis.

### Property Age

Calculates the age of a property based on its sales year and construction year.

```python
df["property_age"] = df["sale_year"] - df["yr_built"]
```

### Renovation Status

Identifies whether a property has been renovated.

```python
df["is_renovated"] = (df["yr_renovated"] > 0).astype(int)
```

### Years Since Renovation

Calculates the number of years since the property was renovated.

### Price Per Square Foot

Calculates the price per square foot of living area and lot area.

```python
df["price_per_sqft_living"] = df["price"] / df["sqft_living"]

df["price_per_sqft_lot"] = df["price"] / df["sqft_lot"]
```

##  Outlier Detection

The project uses the **Interquartile Range (IQR) method** to identify unusual house prices.

The following statistical values are calculated:

- Q1 – First Quartile
- Q3 – Third Quartile
- IQR – Interquartile Range

```python
Q1 = df["price"].quantile(0.25)
Q3 = df["price"].quantile(0.75)
IQR = Q3 - Q1
```

House prices outside the IQR limits are identified as outliers.

The total number of price outliers is displayed.

##  Final Data Validation

After cleaning and preprocessing, the project checks:

- Final dataset shape
- Remaining missing values
- Statistical summary
- Number of identified price outliers

The cleaned dataset is exported into a new CSV file.

```python
df.to_csv("House_Sales_Data_Cleaned_Week_09.csv", index=False)
```

##  Analysis Summary

| Technique | Purpose |
|---|---|
| Data Exploration | Understand dataset structure |
| Missing Value Checking | Identify incomplete records |
| Duplicate Removal | Remove repeated records |
| Date Conversion | Process sales dates |
| Feature Engineering | Create new analytical columns |
| Property Age Calculation | Calculate property age |
| Renovation Analysis | Identify renovation status |
| Price Calculation | Calculate price per square foot |
| IQR Method | Detect price outliers |
| CSV Export | Save cleaned dataset |

##  How to Run the Project

1. Open the Python file in Google Colab.
2. Upload the `kc_house_data.csv` dataset.
3. Ensure the dataset filename matches the filename used in the code.
4. Run the code cells step by step.
5. Check the cleaned dataset and analysis results.
6. Download the generated cleaned CSV file if required.

##  Project Structure

```text
House-Sales-Data-Analysis-Week-09/
│
├── house_sales_data_dv_week_09.py
├── kc_house_data.csv
├── House_Sales_Data_Cleaned_Week_09.csv
└── README.md
```
