#  Student Performance Data Analysis

##  Project Overview
This project focuses on analyzing student academic performance using Python. It explores students' mathematics, reading, and writing scores through data analysis techniques to understand the dataset, calculate total scores and percentages, and identify outliers in mathematics scores.

##  Objectives
- Load and explore the student performance dataset.
- Understand the structure and statistical summary of the data.
- Identify missing values and duplicate records.
- Analyze mathematics, reading, and writing scores.
- Calculate total scores and percentages.
- Detect outliers in mathematics scores using the IQR method.

##  Technologies Used
- **Python** – Programming language
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical computing
- **Matplotlib** – Data visualization library
- **Seaborn** – Statistical visualization library
- **Google Colab / Jupyter Notebook** – Development environment

##  Dataset Description
The project uses the `StudentsPerformance.csv.xls` dataset, which contains student performance information.

Key score columns used:
- `math score`
- `reading score`
- `writing score`

The analysis also creates two additional columns:
- **Total Score:** Sum of mathematics, reading, and writing scores.
- **Percentage:** Total score converted into a percentage out of 300.

## Project Workflow

### 1. Data Loading
Import the required Python libraries and load the student performance dataset using Pandas.

### 2. Data Exploration
- Display the first and last few records.
- Check dataset dimensions and column information.
- Generate descriptive statistics.
- Inspect missing values and duplicate records.

### 3. Score Analysis
- Analyze the three subject scores.
- Calculate descriptive statistics.
- Find the first quartile (Q1) of the subject scores.

### 4. Total Score and Percentage Calculation
Calculate each student's total score and percentage.

**Formula:**

Total Score = Math Score + Reading Score + Writing Score

Percentage = (Total Score / 300) × 100

### 5. Outlier Detection
Use the Interquartile Range (IQR) method to identify potential outliers in mathematics scores.

- Q1 = First quartile
- Q3 = Third quartile
- IQR = Q3 − Q1

Lower Bound = Q1 − 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR

Values outside these bounds are identified as potential outliers.

##  Expected Outcomes
- Understand the dataset's structure and statistical properties.
- Inspect missing and duplicate records.
- Summarize student performance across three subjects.
- Calculate total scores and percentages.
- Identify potential outliers in mathematics scores.

##  Installation and Execution

### Prerequisites
Install Python and the required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

### Run the Project
1. Download or clone this repository.
2. Place the dataset in the appropriate project directory.
3. Open `Student_Performance_Data_DV_Week_07.ipynb` in Jupyter Notebook or Google Colab.
4. Update the dataset path if necessary.
5. Run the notebook cells in order.

##  Project Structure

```text
Student-Performance-Data-Analysis/
│
├── Student_Performance_Data_DV_Week_07.ipynb
├── student_performance_data_dv_week_07.py
├── StudentsPerformance.csv.xls
└── README.md
```

##  Future Enhancements
- Create visualizations to compare subject scores.
- Explore relationships between student performance and other available attributes.
- Analyze score distributions and correlations.
- Build a dashboard for interactive student performance analysis.

