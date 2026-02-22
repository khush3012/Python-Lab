# Experiment 9: Study of Pandas Library

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Class:** Entc - A3  
**Date:** 18/02/2026  

---

## 1. Objective
To study the Pandas library in Python, understand its primary data structures (Series and DataFrame), and perform essential operations including data creation, inspection, manipulation, statistical analysis, and missing value treatment.

## 2. Theory
Pandas (derived from "Panel Data") is a powerful open-source Python library used primarily for working with structured data. It is widely used in Data Science and Machine Learning for:

* **EDA (Exploratory Data Analysis):** Analyzing datasets to summarize their main characteristics.
* **Data Cleaning:** Handling missing, duplicate, or malformed data.
* **Data Manipulation:** Filtering, transforming, and aggregating structured data.



## 3. Implementation and Functions Explained
Below is a detailed explanation of all the Pandas attributes and functions used during the experiment:

### A. Data Creation
* `pd.Series(data)`: Creates a one-dimensional array-like object containing a sequence of values. In the experiment, it was used to create a simple list of numbers `[10, 20, 30, 40]`.
* `pd.DataFrame(data)`: Creates a two-dimensional, size-mutable, and potentially heterogeneous tabular data structure with labeled axes (rows and columns). It was used to convert a dictionary of student names and marks into a structured table.

### B. Data Inspection and Structure
* `df.head()`: Returns the first 5 rows of the DataFrame by default. Useful for quickly testing if your object has the right type of data in it.
* `df.tail()`: Returns the last 5 rows of the DataFrame by default. Useful for verifying the end of your dataset.
* `df.shape`: An attribute that returns a tuple representing the dimensionality of the DataFrame (rows, columns). For the student data, it returned `(4, 2)`.
* `df.ndim`: Returns an integer representing the number of axes/array dimensions. A DataFrame returns `2` (rows and columns).
* `df.size`: Returns the total number of elements in the object (rows multiplied by columns). For a 4x2 DataFrame, it returned `8`.
* `df.columns`: Returns the column labels (names) of the DataFrame.
* `df.dtypes`: Returns the data types of each column (e.g., `object` for strings/names, `int64` for numerical marks).

### C. Data Selection and Modification
* `df["ColumnName"]`: Accesses a specific, individual column (e.g., `df["Name"]` or `df["Marks"]`), returning it as a Pandas Series.
* `df.loc[]`: Accesses a group of rows and columns by label(s) or a boolean array.
  * `df.loc[1]`: Fetched the entire row at index 1 (Philips).
  * `df.loc[0, "Marks"] = 88`: Updated a specific value (changed Glen's marks to 88) by specifying both the row index and the column name.
* **Adding a Column:** A new column was added simply by assigning a list of values to a new column name: `df["Grade"] = [...]`.
* `df.drop()`: Used to remove rows or columns. By specifying `axis=1`, it drops the specified column (e.g., "Grade"). The `inplace=True` argument ensures the original DataFrame is modified directly without needing to reassign it.

### D. Statistical Analysis & Filtering
* `df["Marks"].mean()`: Calculates and returns the mathematical average of the numerical values in the "Marks" column.
* `df["Marks"].mode()`: Returns the most frequently occurring value(s) in the specified column.
* `df["Marks"].min()` & `df["Marks"].max()`: Returns the lowest and highest values in the column, respectively.
* **Filtering** (`df[df["Marks"] > 80]`): Applies a boolean condition to filter the DataFrame. This specific command returned only the rows where the student's marks were strictly greater than 80.

### E. Handling Missing Values (NaN)
* `np.nan`: A special floating-point value from the NumPy library used to represent missing or null values in the dataset.
* `df.isna()`: A boolean function that checks for missing values. It returns a DataFrame of the same size, with `True` where a NaN exists and `False` otherwise.
* `df.notna()`: The exact opposite of `isna()`. It returns `True` for valid/existing data and `False` for missing data.
* `df.isna().sum()`: Chaining the `.sum()` function after `.isna()` counts the total number of missing values in each individual column.
* `df.dropna()`: Removes missing values. By default, it drops any row that contains at least one NaN value, resulting in a cleaner, complete dataset.

## 4. Conclusion
In this experiment, the fundamentals of the Pandas library were successfully explored. Practical operations such as creating DataFrames, checking dataset dimensionality, accessing and updating specific records, calculating basic statistics, and handling missing data (NaN) were executed. These foundational techniques are essential for performing efficient Data Cleaning and Exploratory Data Analysis (EDA) in real-world datasets.
