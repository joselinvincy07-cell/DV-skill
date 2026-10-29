#  Student Performance Data Visualization – Week 8

##  Project Overview

This project focuses on analyzing and visualizing student academic performance using Python. It explores the relationship between students' mathematics, reading, and writing scores and different demographic factors.

The analysis considers parental education level, gender, lunch type, and test preparation course to understand patterns in students' academic performance.

##  Objectives

- Explore and understand the student performance dataset.
- Analyze mathematics, reading, and writing scores.
- Study average exam scores based on parental education level.
- Examine academic performance based on lunch type.
- Compare scores according to test preparation course.
- Understand relationships between different subject scores.
- Visualize data patterns using charts and graphs.

##  Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab

##  Dataset

The project uses the **Students Performance Dataset** stored in CSV format.

**Dataset file:** `StudentsPerformance.csv`

The dataset contains academic scores and demographic information, including:

- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch
- Test Preparation Course
- Math Score
- Reading Score
- Writing Score

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/StudentsPerformance.csv")
```

##  Data Exploration

The dataset is explored using Pandas functions such as:

```python
df.head()
df.tail()
df.info()
df.shape
df.columns
```

These functions help examine the dataset's records, structure, dimensions, and column names.

The project also identifies unique values in demographic columns to understand the different categories in the dataset.

##  Data Analysis and Visualizations

### 1. Average Exam Scores by Parental Level of Education

A bar chart is used to compare the average mathematics, reading, and writing scores across different parental education levels.

**Purpose:** To examine how average student scores vary according to parental education level.

### 2. Score Variance Based on Test Preparation

The project includes a chart section titled **Score Variance Based on Test Preparation** to explore academic performance in relation to test preparation.

It also calculates average subject scores grouped by test preparation course.

### 3. Pair Plot of Subject Scores

A pair plot is created using Seaborn to explore relationships between:

- Math Score
- Reading Score
- Writing Score

**Purpose:** To visualize score distributions and relationships between the three subjects.

### 4. Correlation Heatmap

A correlation heatmap is created to examine the relationships between mathematics, reading, and writing scores.

```python
scores = df[
    ["math score", "reading score", "writing score"]
]

corr = scores.corr()

sns.heatmap(
    corr,
    annot=True,
    cmap="coolwarm",
    fmt=".2f"
)
```

**Purpose:** To display correlation values and understand how scores in different subjects are related.

### 5. Performance Based on Parental Education

The average math, reading, and writing scores are calculated for each parental education level.

### 6. Performance Based on Lunch Type

The project calculates average subject scores for different lunch categories to compare academic performance.

### 7. Performance Based on Test Preparation

Average mathematics, reading, and writing scores are grouped by test preparation course to examine differences in academic performance.

##  Analysis Summary

| Analysis | Purpose |
|---|---|
| Dataset Exploration | Understand the dataset structure |
| Parental Education Analysis | Compare average scores by parental education |
| Test Preparation Analysis | Examine scores by preparation course |
| Pair Plot | Explore relationships between subject scores |
| Correlation Heatmap | Analyze correlations between subjects |
| Lunch Type Analysis | Compare average scores by lunch category |

##  How to Run the Project

1. Open the Python file in Google Colab.
2. Upload the `StudentsPerformance.csv` dataset.
3. Ensure the CSV filename matches the filename used in the code.
4. Run the code cells in sequence.
5. View the analysis results and generated visualizations.

##  Project Structure

```text
Student-Performance-Data-Visualization/
│
├── student_performance_data_dv_week_08.py
├── StudentsPerformance.csv
└── README.md
```
