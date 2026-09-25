#  Shopify Stock Data Visualization – Week 4

##  Project Overview

This project focuses on visualizing **Shopify stock price data** using Python. The project uses a line chart to represent the **closing price of Shopify stock over time**.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Google Colab

##  Dataset

The project uses a CSV file named **`shopify_stock.csv`** containing Shopify stock data.

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/shopify_stock.csv")
```

The first few records are displayed using `df.head()` to understand the dataset.

##  Visualization

### Shopify Stock Price

A **Line Plot** is used to visualize the movement of Shopify's closing stock price over time.

* **X-axis:** Date
* **Y-axis:** Closing Price
* **Chart Title:** Shopify Stock Price

```python
plt.plot(df["date"], df["close"])

plt.xlabel("Date")
plt.ylabel("Closing Price")
plt.title("Shopify Stock Price")

plt.show()
```

##  Objectives

* Load Shopify stock data using Pandas.
* Explore the stock dataset.
* Visualize closing stock prices.
* Understand stock price movement over time.
* Create a line chart using Matplotlib.

##  Visualization Technique

| Chart     | Purpose                                        |
| --------- | ---------------------------------------------- |
| Line Plot | To visualize Shopify's closing price over time |

##  How to Run

1. Open the Python file in **Google Colab** or a Python environment.
2. Upload the `shopify_stock.csv` dataset.
3. Make sure the dataset filename matches the filename used in the code.
4. Run the program.
5. View the generated Shopify Stock Price chart.

## Project Structure

```text
Shopify-Stock-Data-Visualization/
│
├── shopify_stock_data_dv_week_04.py
├── shopify_stock.csv
└── README.md
```


BCA Student

