# Data Cleaning and Preprocessing

## Project Overview
This project focuses on cleaning and preprocessing raw e-commerce datasets to improve data quality, consistency, and usability for further data analysis.

The project contains three datasets: sales interactions, customer details, and product details. Each dataset was inspected and processed to handle missing values, remove unnecessary data, and improve data structure.

## Repository Structure

```text
Data_Cleaning_and_Preprocessing/
│
├── data/
│   ├── raw/
│   │   ├── E-commerece sales data 2024.csv
│   │   ├── customer_details.csv
│   │   └── product_details.csv
│   │
│   └── cleaned/
│       ├── E-commerece sales data 2024_Cleaned.csv
│       ├── customer_details_cleaned.csv
│       └── product_details_cleaned.csv
│
└── README.md
```

## Datasets

| Dataset | Records | Columns |
|---|---:|---:|
| E-commerce Sales | 2,999 | 4 |
| Customer Details | 3,900 | 18 |
| Product Details | 10,002 | 16 |

## Data Cleaning and Preprocessing

### 1. E-commerce Sales Dataset
- Removed completely blank rows and unnecessary summary rows.
- Handled missing values in the `Interaction type` column by assigning `Unknown`.
- Removed unnecessary columns.
- Checked for duplicate records.
- Verified the final dataset structure.

### 2. Customer Details Dataset
- Checked for missing values and duplicate records.
- Reviewed data types of numerical columns.
- Inspected categorical values for consistency.
- Verified the cleaned dataset.

### 3. Product Details Dataset
- Removed completely empty and unnecessary columns.
- Removed extra unnamed columns and an incorrect trailing summary row.
- Replaced missing values in the `Category` column with `Unknown`.
- Created a numeric helper column, `Selling Price Numeric`, to support price-based analysis.
- Retained missing values in sparsely populated product attributes where reliable replacement values were unavailable.
- Checked for duplicate records.

## Data Quality Summary

| Dataset | Missing Values | Duplicate Rows |
|---|---:|---:|
| E-commerce Sales | 0 | 0 |
| Customer Details | 0 | 0 |
| Product Details | 32,834 | 0 |

**Note:** Missing values in the product dataset were intentionally retained in sparsely populated fields rather than filled with arbitrary values.

## Tools Used
- Microsoft Excel
- GitHub

## Key Learning Outcomes
- Understanding data quality issues in real-world datasets.
- Handling missing values and duplicate records.
- Cleaning unnecessary columns and rows.
- Working with numerical and categorical data.
- Preparing datasets for further analysis.

## Project Status
**Task 1 – Data Cleaning and Preprocessing: Completed**

More analysis and visualization tasks may be added as the project progresses.
