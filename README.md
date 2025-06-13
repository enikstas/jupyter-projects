# jupyter-projects
# Data Cleaning Project

## Overview
This project demonstrates data cleaning techniques using Python on a sales dataset with 477 rows and 8 columns: `customer_id`, `date`, `product`, `quantity`, `unit_price`, `payment_method`, `comment`, and `amount`. The goal was to prepare the dataset for analysis by fixing errors, handling missing values, and standardizing data.

## Project Objectives
- Clean and preprocess a sales dataset.
- Fix inconsistent date formats and data types.
- Handle missing values (~27% in `comment`, ~8.8% in `amount`).
- Correct errors in `amount` and standardize labels.
- Optimize dataset for time-based analysis.

## Dataset Description
- **Rows**: 477 (after removing 2 duplicates).
- **Columns**: 8 (initially), reduced to 7 after dropping `comment`.
- **Key Issues**:
  - Mixed date formats in `date` (e.g., '2025-07-20', '2025-07-20 00:00:00').
  - Missing values: `comment` (129, ~27%), `amount` (42, ~8.8%), `quantity` (24, ~5.0%).
  - Errors in `amount` (e.g., 71043.39 instead of `quantity` * `unit_price`).
  - Inconsistent labels in `payment_method` (e.g., 'cc' vs 'CC').

## Steps
1. **Initial Exploration**: Loaded data and checked structure with `df.info()` and `df.describe()`.
2. **Summary Statistics**: Analyzed numerical columns to identify outliers (e.g., `amount = 71043.39`).
3. **Clean Column Names**: Standardized names (e.g., 'Cust ID' to `customer_id`).
4. **Fix Data Types**: Parsed `date` to `datetime.date` using `dateutil.parser`, ensuring no missing values.
5. **Remove Duplicates**: Dropped 2 duplicate rows, reducing dataset to 477 rows.
6. **Check Missing Values**: Quantified missing values with `df.isnull().sum()`, confirming no missing `date` values.
7. **Check Outliers**: Identified 26 outliers in `quantity` and `unit_price` (mostly `unit_price = 1500.0`), preserved all rows.
8. **Handle Missing Values**: Filled `quantity` (24), `unit_price` (18) with means, `customer_id` (27), `payment_method` (28) with modes, `comment` (129) with 'No Comment', and `date` (0, prophylactically). Recalculated `amount` for all rows. Converted `date` to `datetime64`.
9. **Fix Label Inconsistencies**: Standardized `payment_method` to `cash` (206), `credit_card` (175), and `online_payment` (96).
10. **Drop Unnecessary Columns**: Removed `comment`, reducing to 7 columns.
11. **Create New Columns**: Added `amount_check` to validate `amount`.
12. **Split Date**: Extracted `year` and `month` for time-based analysis.
13. **Save Cleaned Data**: Saved dataset to `cleaned_data.csv`.

## Technologies Used
- **Python**: Core programming language.
- **Pandas**: Data manipulation and analysis.
- **dateutil**: Parsing mixed date formats.
- **NumPy**: Supporting numerical operations.

## Key Results
- Cleaned dataset with 477 rows and 7 columns, free of missing values and errors.
- Corrected `amount` errors (e.g., 71043.39).
- Standardized `date` to `datetime64` and `payment_method` to three categories.
- Removed `comment`, optimizing dataset for analysis.

Contact

Feel free to reach out for questions or feedback:

    https://www.linkedin.com/in/enikstas/
