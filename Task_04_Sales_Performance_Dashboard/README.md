# Task 4: Sales Performance Dashboard

## Objective
Design an interactive sales dashboard for business stakeholders using Power BI, with summary KPIs, time-based analysis, territory and product-line comparisons, and interactive filters.

## Tools
- Microsoft Power BI Desktop
- DAX
- CSV dataset

## Dataset
The project uses `sales_data_analyzed.csv`, containing 20 sales records and 9 fields:

- Order date and customer name
- Territory and product line
- Revenue and profit
- Year, month, and quarter

The supplied records cover January–August 2023. The dataset has no missing values or duplicate rows.

## Dashboard Features

### KPI cards
- **Total Revenue:** 13,968.96
- **Total Profit:** 4,190.72
- **Profit Margin:** 30.00%
- **Total Orders:** 20 records

> Note: The source dataset does not specify a currency. The KPI values are therefore presented without a currency symbol. The Total Orders measure counts rows because the supplied dataset does not include a unique order ID.

### Visualizations
1. **Monthly Revenue Trend** — line chart showing revenue by month, sorted chronologically.
2. **Revenue by Territory** — bar chart comparing revenue across territories.
3. **Revenue by Product Line** — donut chart showing revenue contribution by product line.
4. **Profit by Product Line** — column chart comparing profit across product lines.

### Interactivity
- Year slicer
- Territory slicer

The slicers allow users to filter the KPI cards and report visuals.

## DAX Measures

```dax
Total Revenue = SUM('sales_data_analyzed'[Revenue])

Total Profit = SUM('sales_data_analyzed'[Profit])

Profit Margin =
DIVIDE(
    [Total Profit],
    [Total Revenue],
    0
)

Total Orders = COUNTROWS('sales_data_analyzed')
```

The month sorting helper column:

```dax
Month Number = MONTH('sales_data_analyzed'[ORDERDATE])
```

The `MONTH` column is sorted by `Month Number` to keep months in calendar order.

## Repository Structure

- `Dataset/` — source CSV
- `PowerBI/` — editable Power BI report
- `Screenshots/` — dashboard preview
- `Images/Background/` — dashboard background asset
- `Images/Icons/` — KPI icon assets

## Limitations
This is a small demonstration dataset with 20 records covering eight months of 2023. The findings are descriptive of the supplied records and should not be treated as representative of a full year or a larger business population.
