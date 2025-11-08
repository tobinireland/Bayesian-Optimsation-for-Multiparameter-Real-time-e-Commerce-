# Bayesian Optimisation for Multiparameter Real-time e-Commerce

**Author:** Tobin Ireland  
**Course:** Imperial College - Professional CErtificated in ML and AI  — Capstone Project  

## Project Overview

This capstone project explores **Bayesian Optimisation** applied to multiparameter decision-making in real-time e-commerce settings.  
We aim to optimise metrics like pricing, promotions, and inventory allocation based on historical retail data.

## Dataset

We are using the **Online Retail II** dataset from the **UCI Machine Learning Repository**.

- **Source:** [UCI Machine Learning Repository - Online Retail II](https://archive.ics.uci.edu/ml/datasets/online+retail+ii)  
- **Years:** 2010-2011  
- **Number of rows:** ~500,000  
- **Number of columns:** 8  

### Column Descriptions

| Column Name  | Description |
|--------------|-------------|
| InvoiceNo    | Invoice number (unique identifier for each transaction) |
| StockCode    | Product (item) code |
| Description  | Product (item) name |
| Quantity     | Quantity of each product per transaction |
| InvoiceDate  | Invoice date and time |
| UnitPrice    | Unit price of the product |
| CustomerID   | Customer number |
| Country      | Country name |

## Project Structure

.
├── data
│   ├── raw                              # Original Excel dataset
│   └── raw/online_retail_II_sample.csv  # Sample dataset for GitHub
├── notebooks
│   └── explore_dataset.ipynb
├── README.md
└── .gitignore

## How to Use

1. Clone this repository:

   git clone https://github.com/tobinireland/Bayesian-Optimsation-for-Multiparameter-Real-time-e-Commerce-.git

2. Activate the Python environment:

   conda activate capstone

3. Open the Jupyter Notebook:

   jupyter notebook

4. Navigate to `notebooks/explore_dataset.ipynb` to explore the dataset.
5. Navigate to 'notebooks/main_optimization.ipynb' to run a basic 2 hyper-parameter bayesian optimization
6. Navigate to 'notebooks/main_optimization_5_parameters.ipynb' to run a basic 5 hyper-parameter bayesian optimization


## Problem Definition

Our goal is to predict the best product, price, and promotional offer for each customer to maximize customer lifetime profitability. This is a multi-objective problem: determining what the next promotion should be for each customer.

## Modeling Approach

We will use **Bayesian Optimization** to optimize multiple objectives simultaneously. This approach allows us to efficiently explore the space of possible product, price, and promotional combinations for each customer to maximize expected profitability.

### Why Bayesian Optimization

- Handles **multi-objective optimization** effectively.
- Works well for problems with **several tunable hyperparameters** (typically 2–8), which fits our dataset.
- Efficiently searches the space without requiring exhaustive evaluation.

### Dataset

- The dataset is sourced from the UCI Machine Learning Repository, containing **two years of retail e-commerce transactions**.
- Sample data for GitHub: `data/raw/online_retail_II_sample.csv`
- The dataset includes columns such as `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.






