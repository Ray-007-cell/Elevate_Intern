# Task 05 – Exploratory Data Analysis (EDA): Titanic Dataset

## Objective

Explore the Titanic passenger dataset using statistical summaries and visualizations to identify patterns, relationships, missing data, and factors associated with passenger survival.

## Tools and Technologies

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Jupyter Notebook

## Dataset

The original Titanic training dataset contains **891 passenger records and 12 columns**.

- `train.csv`: Original dataset.
- `titanic_cleaned.csv`: Processed dataset with 891 rows and 16 columns, including engineered features.

## Project Structure

```text
Task_05_Exploratory_Data_Analysis/
├── Dataset/
│   ├── train.csv
│   └── titanic_cleaned.csv
├── Notebook/
│   └── Titanic_EDA.ipynb
├── Report/
│   ├── Titanic_EDA.pdf
│   └── Titanic_EDA.html
├── Visualizations/
│   ├── Age_Distribution.png
│   ├── Categorical_Distributions.png
│   ├── Correlation_Heatmap.png
│   ├── Fare_Boxplot.png
│   ├── Fare_Distribution.png
│   ├── Fare_by_Pclass.png
│   ├── Missing_Values_Heatmap.png
│   ├── Survival_by_AgeGroup.png
│   ├── Survival_by_Cabin.png
│   ├── Survival_by_FamilyType.png
│   ├── Survival_by_Gender.png
│   ├── Survival_by_Pclass.png
│   └── Titanic_Pairplot.png
└── README.md
```

## Analysis Performed

1. Dataset inspection using `info()`, `describe()`, and value counts.
2. Missing-value and duplicate checks.
3. Univariate analysis of categorical and numerical variables.
4. Age and fare distributions, including potential fare outlier detection using the IQR method.
5. Survival comparisons by gender, passenger class, age group, cabin availability, and family type.
6. Correlation heatmap and pairplot for exploring relationships among numerical variables.
7. Data cleaning and feature engineering.

## Key Findings

- Overall survival rate was **38.38%** (342 of 891 passengers).
- Female survival rate was **74.20%**, compared with **18.89%** for male passengers.
- Survival by passenger class was **62.96%** in 1st class, **47.28%** in 2nd class, and **24.24%** in 3rd class.
- Survival by age group: Child **57.97%**, Teenager **42.86%**, Young Adult **38.27%**, Adult **40.00%**, and Senior **22.73%**.
- The fare distribution was right-skewed. The IQR method flagged **116 potential outliers** using an upper fence of approximately **65.63**.
- Passengers with cabin information recorded had a **66.67%** survival rate, compared with **29.99%** among passengers with unknown cabin information.
- Survival by family type was **57.88%** for small families, **30.35%** for passengers travelling alone, and **16.13%** for large families.

These are descriptive associations in this dataset; they do not establish causation.

## Data Cleaning and Feature Engineering

- Filled missing `Age` values using median age grouped by passenger class and sex.
- Filled the two missing `Embarked` values using the mode (`S`).
- Retained missing `Cabin` values because 687 records (77.10%) were missing; added `Cabin_Known` to indicate whether cabin information was available.
- Created `AgeGroup`, `FamilySize`, and `FamilyType` features.
- Checked for duplicate rows; none were found.
- The cleaned dataset contains **891 rows and 16 columns**. The missing Cabin values were intentionally retained.

## How to Run

1. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

2. Open `Notebook/Titanic_EDA.ipynb` in Jupyter Notebook or VS Code.
3. Run the notebook cells in order. The notebook reads the original dataset from the `Dataset` folder.

## Deliverables

- [Jupyter Notebook](Notebook/Titanic_EDA.ipynb)
- [PDF Report](Report/Titanic_EDA.pdf)
- [HTML Report](Report/Titanic_EDA.html)
- [Original Dataset](Dataset/train.csv)
- [Cleaned Dataset](Dataset/titanic_cleaned.csv)
- [Visualizations](Visualizations/)

## Limitations

- The analysis uses the provided Titanic training dataset and should not be generalized to all passengers or other populations.
- A substantial proportion of Cabin values are missing.
- Imputation choices can affect statistical summaries and visual patterns.
- Correlation and group survival differences indicate associations, not causal relationships.
