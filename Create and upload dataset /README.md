# Experiment 10: Create and Upload Dataset

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Class:** Entc - A3  
**Date:** 20th February, 2026  

---

## Objective
To understand the fundamentals of data manipulation using the Python `pandas` library, including creating dataframes, exporting/importing datasets, exploring data structures, performing statistical analysis, and modifying data.

---

## 1. Data Creation and Export
This section covers how a dataset is initialized from scratch and saved to the local environment.

* **`pd.DataFrame(data)`**: This function is used to create a two-dimensional, size-mutable, and potentially heterogeneous tabular data structure (a DataFrame) from a Python dictionary. In this experiment, a dictionary containing student details (Number, Gender, Department, CGPA) was converted into a structured table.
* **`df.to_csv("filename.csv", index=False)`**: This function exports the DataFrame into a Comma-Separated Values (CSV) file. The `index=False` parameter ensures that the auto-generated row numbers (0, 1, 2...) are not saved as a separate column in the file.

## 2. Data Exploration and Properties
These functions are used to understand the basic shape, size, and composition of the dataset.



* **`df.info()`**: Prints a concise summary of the DataFrame. It shows the number of rows (entries), the number of columns, the data type of each column (e.g., `int64`, `object`, `float64`), and the amount of memory the dataset is using. It is crucial for checking for missing (null) values.
* **`df.shape`**: An attribute (not a function, hence no parentheses) that returns a tuple representing the dimensionality of the DataFrame in the format `(rows, columns)`. For the student dataset, it returned `(5, 4)`.
* **`df.size`**: An attribute that returns the total number of elements in the DataFrame (rows multiplied by columns). For a 5x4 dataset, the size is `20`.
* **`df.dtypes`**: Returns a series with the data type of each column. This is helpful to confirm if numerical values are correctly stored as integers or floats, and text as objects.

## 3. Data Access and Filtering
These commands demonstrate how to isolate specific parts of the dataset for analysis.

* **`df["ColumnName"]`**: Used to access and extract a single column from the DataFrame. For example, `df["Department"]` retrieved only the department names.
* **`df[df["ColumnName"] == Value]`**: This is called **Boolean Indexing**. It filters the dataset to only show rows that meet a specific condition. For example, `df[df["Number"] == 103]` filtered the dataset to display only the details of the student with PRN `103`.

## 4. Statistical Operations
Pandas provides built-in functions to perform quick mathematical operations on the data. 

> **Note:** The parameter `numeric_only=True` was used in these functions to ensure the operations were only applied to numerical columns (Number, CGPA) and not categorical text columns (Gender, Department), which would cause an error.

* **`df.mean()`**: Calculates the average value of the numerical columns.
* **`df.median()`**: Finds the middle value of the numerical columns when they are sorted in ascending order.
* **`df.mode()`**: Identifies the most frequently occurring value(s) in the dataset.
* **`df["ColumnName"].max()`**: Returns the highest value within a specific column. In the experiment, `df["CGPA"].max()` was used to find the topper's CGPA (9.6).

## 5. Data Modification
This involves altering the structure of the existing DataFrame.

* **Adding a New Column (`df["Grade"] = [...]`)**: A new column named "Grade" was successfully added to the right side of the DataFrame by directly assigning a list of values to a new column key.
* **`df.drop("ColumnName", axis=1)`**: This function removes specified labels from rows or columns. By setting `axis=1`, the function was instructed to drop a column (specifically, the "Gender" column) rather than a row.

## 6. Working with External Datasets
The final part of the experiment involved loading and analyzing a larger, pre-existing dataset (`Cars93.csv`).

* **`pd.read_csv('filepath')`**: Reads a comma-separated values (CSV) file into a Pandas DataFrame. This is the standard way to import external datasets for analysis.
* **`df.head()`**: Returns the first 5 rows of the DataFrame by default. It is highly useful for quickly verifying that the data was loaded correctly and checking the column headers.
* **`df.tail()`**: Returns the last 5 rows of the DataFrame by default. This helps verify the end of the dataset.
* **`df.describe()`**: Generates descriptive statistics for all numerical columns in the dataset. It provides a comprehensive summary including the count, mean, standard deviation, minimum, maximum, and quartile percentiles (25%, 50%, 75%) all at once.

---

## Conclusion
This experiment successfully demonstrated the core functionalities of the Python `pandas` library for data manipulation and analysis. By creating a custom student dataset and exploring a pre-existing one (`Cars93.csv`), practical experience was gained in structuring tabular data, extracting specific information through Boolean indexing, and computing fundamental descriptive statistics. Furthermore, mastering operations like modifying data frame structures (adding/dropping columns) and handling file exports/imports establishes a strong technical foundation for preprocessing and analyzing larger, more complex datasets in future engineering and data science projects. These foundational skills in `pandas` are essential for automating data workflows and extracting meaningful insights from raw information. Ultimately, the ability to clean, filter, and analyze datasets efficiently serves as a vital stepping stone for advanced applications in machine learning, statistical modeling, and data-driven decision-making.
