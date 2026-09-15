E-commerce Sales Analysis

Exploratory data analysis of the Superstore dataset. This project investigates sales performance, profitability, discounts, categories, regions, customer segments, and shipping behavior.

Objectives

- Analyze overall sales and profit performance
- Identify the most and least profitable categories and sub-categories
- Evaluate the relationship between discounts and profitability
- Analyze sales and profit trends over time
- Compare performance across regions, customer segments, and shipping modes

Dataset

The analysis uses the Superstore dataset with 9,994 sales records and 21 variables, including order information, customer data, products, sales, discounts, and profit.

Tools

- Python
- Pandas
- Matplotlib
- Jupyter Notebook
- Git / GitHub

Project Structure

Ecommerce-sales/
├── data/
│   └── Sample - Superstore.csv
├── notebooks/
│   └── 01_analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore

How to Run

1. Clone the repository

git clone https://github.com/enzoy-dev/Ecommerce-sales.git
cd Ecommerce-sales

2. Install the dependencies

pip install -r requirements.txt

3. Open the notebook

jupyter notebook

Then open:

notebooks/01_analysis.ipynb

Key Findings

- Total sales were approximately $2.30 million, with approximately $286 thousand in profit.
- Sales increased by 51.4% between 2014 and 2017.
- Profit increased by 88.6% during the same period, growing faster than sales.
- Technology generated the highest total sales and had one of the strongest profit margins.
- Furniture had a substantially lower profit margin than Technology and Office Supplies.
- The West region achieved the highest sales, profit, and profit margin.
- Tables was the least profitable sub-category, with a negative profit margin.
- Higher discount levels were generally associated with lower profitability.
- Customer segments and shipping modes show different performance patterns in both sales volume and margin.

Author

Enzo Sousa dos Santos