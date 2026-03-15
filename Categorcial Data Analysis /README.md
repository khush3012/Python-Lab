# Experiment 11: Categorical Data Analysis using Python

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 06/03/2026  

---

## Theory

### Introduction
Categorical data represents variables that contain label values rather than numeric values (e.g., 'Clothing', 'Electronics', 'Male', 'Female'). Analyzing this type of data involves counting frequencies, finding proportions, and observing the relationships between different categorical variables. The Python library **Pandas** is highly effective for this, providing high-performance, easy-to-use data structures and data analysis tools.

---

## Core Pandas Functions Used in the Experiment

### 1. Data Creation and Ingestion
* `import pandas as pd`: Imports the Pandas library into the Python environment and assigns it the alias `pd` for quicker typing.
* `pd.DataFrame(Data)`: Converts standard Python data structures (like dictionaries or lists) into a structured 2-dimensional labeled data structure called a DataFrame. It organizes the data into rows and columns, similar to a spreadsheet. 
* `pd.read_csv("filename.csv")`: Reads a comma-separated values (CSV) file and loads it directly into a Pandas DataFrame.
* `df.head()`: A preview function that returns the first 5 rows of the DataFrame. It is highly useful for getting a quick snapshot of the data's structure and contents.

### 2. Frequency and Distribution (Univariate Analysis)
* `df['Column'].value_counts()`: One of the most important functions for categorical data. It returns an object containing counts of unique values in a specific column in descending order. It tells you exactly how many of each category exist.
* `df['Column'].value_counts(normalize=True) * 100`: By setting the `normalize` parameter to `True`, the function returns the relative frequencies (proportions) of the unique values. Multiplying by `100` converts these proportions into percentages, making it easy to see the percentage distribution of categories.

### 3. Identifying Unique Values
* `df['Column'].unique()`: Returns an array of all the distinct, unique values present in a specific column. This is useful for understanding the exact labels present in your dataset without looking at every single row.
* `df['Column'].nunique()`: Returns the mathematical count of unique values. For example, if the categories are 'UPI' and 'COD', `nunique()` will return `2`.

### 4. Bivariate Analysis (Relationships Between Variables)
* `pd.crosstab(index, columns)`: Computes a simple cross-tabulation (also known as a contingency table) of two (or more) factors. By passing two categorical columns, it displays the frequency distribution of the variables together. 
    > **Example:** Checking how many "New" vs "Returning" customers opted for "Express" vs "Standard" delivery. 
* *Note:* Using `normalize=True` inside `crosstab()` calculates the percentage distribution across the entire table.

### 5. Data Manipulation and Filtering
* **Filtering** (`df[df['Column'] == 'Value']`): Uses Boolean indexing to filter the DataFrame. It isolates and extracts only the rows where the specified condition is met (e.g., extracting only the rows where the category is exactly 'Electronics').
* `df.groupby('Column')`: Splits the data into separate groups based on the unique values of a specified categorical column. When combined with an aggregation function like `.count()`, it allows you to calculate statistics for each group independently (e.g., counting how many payment methods were used per category).
* `df.sort_values(by='Column')`: Sorts the DataFrame sequentially based on the values in a specific column. For categorical text data, this organizes the rows in alphabetical order based on that column's labels.

---

## Conclusion
Through functions like `value_counts()` and `crosstab()`, Pandas provides a robust framework for descriptive statistics on categorical data. These tools allow analysts to quickly summarize string-based data, understand category distributions, and discover intersecting trends between multiple categorical variables.
