# E-commerce Sales Analysis

## Overview

Exploratory data analysis of retail sales data from the Superstore dataset. The project investigates sales performance, profitability, discounts, categories, regions, and sales trends over time.

## Objectives

* Analyze sales and profit performance.
* Identify the most and least profitable categories and sub-categories.
* Evaluate the relationship between discounts and profitability.
* Analyze sales and profit trends over time.
* Compare performance across regions.

## Dataset

The analysis uses the Superstore dataset containing **9,994 sales records** and **21 variables**, including order information, customer data, products, sales, discounts, and profit.

## Tools

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* Git / GitHub

## Analysis

The exploratory analysis covers:

* Data quality and structure
* Sales and profit metrics
* Category performance
* Discount analysis
* Monthly and yearly sales trends
* Regional performance
* Sub-category profitability

## Key Findings

* Total sales were approximately **$2.30 million**, with approximately **$286 thousand in profit**.
* Sales increased by **51.4% between 2014 and 2017**.
* Profit increased by **88.6% during the same period**, growing faster than sales.
* **Technology** generated the highest total sales and had one of the strongest profit margins.
* **Furniture** had a substantially lower profit margin than Technology and Office Supplies.
* The **West** region achieved the highest sales, profit, and profit margin.
* **Tables** was the least profitable sub-category, with a negative profit margin.
* Higher discount levels were generally associated with lower profitability in the dataset. This represents an observed relationship and does not establish causation.

## Project Structure

```text
ecommerce-sales-analysis/
├── data/
├── notebooks/
│   └── 01_analysis.ipynb
├── src/
├── visualizations/
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

Clone the repository, install the required dependencies, and open the Jupyter Notebook:

```bash
pip install -r requirements.txt
jupyter notebook
```

Then open:

```text
notebooks/01_analysis.ipynb
```

## Author

Enzo Sousa dos Santos
