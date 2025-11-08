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

### Hyperparameter Optimization Notebook

In addition to the basic 2-parameter optimization notebook (main_optimization.ipynb), we provide a more advanced 5-hyperparameter Bayesian Optimization notebook:

Notebook: notebooks/main_optimization_5_parameters.ipynb

Purpose: Optimize multiple aspects of pricing and promotions to maximize estimated customer profit.

Hyperparameters included:

Price_Multiplier (continuous) – scales the product price.

Promotion (categorical) – type of promotion applied (No_Discount, Discount_5%, Discount_10%).

Bundle_Size (integer) – simulates the effect of selling multiple units together.

DayOfWeek (categorical) – adjusts expected profitability based on the day of the week.

Max_Discount_Percent (continuous) – limits maximum allowed discount for a promotion.

### How the Notebook Works

Load full dataset: The notebook uses the full Online Retail II dataset (2010–2011) for realistic optimization.

Data preprocessing: Handles missing values, ensures correct types, filters invalid transactions, and computes row-level profit.

Feature engineering: Adds columns for Profit, Promotion, and DayOfWeek.

Day-of-week multipliers: Historical profits per day are normalized to adjust estimated profit in the optimization.

Objective function: Combines all hyperparameters into an estimated profit calculation. The objective is to maximize profit, implemented as minimization of negative profit for the optimizer.

Bayesian Optimization: Runs gp_minimize from scikit-optimize to efficiently search the 5-dimensional hyperparameter space.

Output: Returns the best hyperparameters and the maximum estimated profit.

### Benefits of 5-Hyperparameter Optimization

Demonstrates how Bayesian Optimization handles mixed types of hyperparameters (continuous, integer, categorical).

Incorporates day-of-week effects, which can be extended to seasonality or customer segments.

Provides a scalable framework to include additional business-relevant hyperparameters in the future.

### Hyperparameter Optimization Notebook

The notebook main_optimization_5_parameters.ipynb extends the basic Bayesian optimization workflow to five tunable hyperparameters:

Price_Multiplier (continuous) – adjusts product price for optimization.

Promotion (categorical) – applies a discount type (No_Discount, Discount_5%, Discount_10%).

Bundle_Size (integer) – simulates product bundling strategies.

DayOfWeek (categorical) – incorporates historical sales variation by weekday.

Max_Discount_Percent (continuous) – limits maximum discount applied.

Workflow

Load full dataset: Uses data/raw/online_retail_II.xlsx to maximize insights.

Feature engineering:

Computes row-level profit (Profit = Quantity * Price).

Extracts day of the week from InvoiceDate.

Randomly assigns promotions for demonstration purposes.

Define objective function:

Adjusts price and applies promotions and bundle size.

Computes estimated profit per transaction.

Returns the negative sum of estimated profit to maximize total profit during optimization.

Set search space: Five hyperparameters with appropriate types (continuous, categorical, integer).

Run Bayesian optimization: Efficiently explores the parameter space to find the combination that maximizes estimated profit.

Output:

Best hyperparameter combination.

Corresponding estimated profit.

Optional visualizations of hyperparameter effects.

Notes

The DayOfWeek parameter currently modifies the objective based on historical day-of-week effects. You can extend it to include seasonality, promotions, or customer segments.

This notebook demonstrates multi-objective optimization on a real retail dataset and serves as the core model for the project.

The workflow is reproducible and modular: you can swap in new hyperparameters or apply it to other datasets.

### How to Run

Activate the Python environment: conda activate capstone
Launch Jupyter Notebook: jupyter notebook
Open the Notebook: notebooks/main_optimization_5_parameters.ipynb
Execute cells sequentially to run the full BAyesian optimzation on the complete dataset




