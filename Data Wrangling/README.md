# Experiment 12 - Data Wrangling

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** Entc - A3  
**Date:** 18/03/2026  

---

## Theory on Data Wrangling

### 1. Introduction to Data Wrangling
Data wrangling (also known as data cleaning or data remediation) is the process of transforming, formatting, and mapping raw data into a more usable and standard format for downstream analysis, such as Exploratory Data Analysis (EDA) or machine learning. Real-world data is often incomplete, inconsistent, or formatted incorrectly. This experiment demonstrates how to prepare such datasets using Python's `pandas` and `numpy` libraries.

### 2. Core Libraries Used
* **`pandas` (`pd`)**: The primary Python library for data manipulation and analysis. It provides the `DataFrame` structure, which handles 2D tabular data efficiently.
* **`numpy` (`np`)**: A library for numerical computations. In this context, it is primarily used to represent missing numerical data via `np.nan` (Not a Number).

### 3. Key Operations and Functions Explained

#### A. Data Ingestion and Export
Before any manipulation can occur, data must be loaded into the environment, and once cleaned, it must be saved.
* `pd.DataFrame(data)`: Converts a Python dictionary or list into a structured 2D DataFrame.
* `pd.read_csv('filename.csv')`: Reads a comma-separated values (CSV) file into a pandas DataFrame.
* `df.to_csv('filename.csv', index=False)`: Exports the modified DataFrame back to a CSV file. The `index=False` parameter prevents pandas from writing row numbers as a separate column in the file.

#### B. Identifying Missing Values
Missing data can skew analysis. Identifying where data is missing is the first step in remediation.
* `df.isna()` / `df.isnull()`: These boolean functions scan the DataFrame and return `True` for every cell that contains a null value (`NaN` or `None`) and `False` otherwise.
* `df.isna().sum()`: Chains the sum function to the boolean mask. Because Python treats `True` as `1` and `False` as `0`, this calculates the total number of missing values per column.

#### C. Handling Inconsistent Data Representations
Often, missing data isn't explicitly marked as `NaN` but is instead represented by placeholders like dashes or spaces.
* `df.replace("-", np.nan, inplace=True)`: Scans the DataFrame for the string `"-"` and replaces it with standard `np.nan` objects. The `inplace=True` argument modifies the existing DataFrame directly rather than creating a copy.

#### D. Data Type Conversion
Raw data is frequently imported as strings (`object` data types), even if it represents numbers or dates. These must be converted to standard types for mathematical operations.
* `pd.to_numeric(df['column'], errors='coerce')`: Converts a column's data type to numerical (`float` or `int`). The `errors='coerce'` argument is crucial; if it encounters a string that cannot be converted to a number, it forces that value to become `NaN` instead of throwing a system error.
* `pd.to_datetime(df['column'], errors='coerce')`: Converts string-based dates (e.g., "01-06-2023") into standardized datetime objects (e.g., "2023-01-06"). Invalid date formats are coerced into `NaT` (Not a Time).

#### E. Strategies for Handling Missing Data (Imputation vs. Deletion)
Once `NaN` values are properly identified, they must be resolved. The experiment explores multiple strategies:
* **Deletion (`df.dropna()`)**: Removes entire rows that contain at least one `NaN` value. This is used when the dataset is large enough that dropping a few rows won't impact the overall analysis.
* **Constant Imputation (`df.fillna('DEFAULT')`)**: Replaces missing values with a specific, hardcoded placeholder.
* **Mean Imputation (`df.fillna(df.mean())`)**: Calculates the mathematical average of a numerical column and replaces all `NaN` values in that column with the calculated mean. This was applied to the `Age`, `Luggage.room`, and `Rear.seat.room` attributes. It is best suited for continuous numerical data without extreme outliers.
* **Mode Imputation (`df['col'].fillna(df['col'].mode().values[0])`)**: Replaces missing values with the most frequently occurring value in that column. This was applied to the `AirBags` attribute in the Cars93 dataset because AirBags are categorical data (e.g., "Driver only", "Driver & Passenger"), meaning an average cannot be calculated.

#### F. Text Formatting and Standardization
To ensure consistency in categorical data, text variations must be unified.
* `df['column'].str.upper()`: Accesses the string methods of a column and converts all text to uppercase. This ensures that "Aero" and "AERO" are treated identically during grouping or analysis.

---

### 4. Summary of the Experimental Workflow
The experiment demonstrates a complete data wrangling pipeline:
1.  **Creation/Loading:** Generating raw DataFrames or reading from external sources (like `Cars93.csv`).
2.  **Inspection:** Using `.isna().sum()` to pinpoint data gaps.
3.  **Standardization:** Replacing custom missing indicators (`-`) with `np.nan` and converting text representations of numbers/dates into proper machine-readable formats.
4.  **Imputation:** Applying mathematical strategies (mean for continuous data, mode for categorical data) to fill in the gaps without losing entire rows of valuable data.
5.  **Exporting:** Saving the clean, wrangled data for future analysis.
