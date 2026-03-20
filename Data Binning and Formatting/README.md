# Experiment 13: Data Binning and Data Formatting Using Python

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 20/03/2026  

---

## 1. Objective
To understand and implement the concepts of data binning (discretization) and data formatting on tabular datasets using Python's `pandas` and `numpy` libraries.

## 2. Theoretical Background

### Data Binning (Discretization)
Data binning is a data preprocessing technique used to reduce the effects of minor observation errors. It involves grouping a set of continuous or numerical data values into a smaller number of "bins" or "intervals." This is highly useful for statistical analysis, creating histograms, and converting continuous numerical variables into categorical variables to simplify machine learning models.

### Data Formatting
Data formatting involves cleaning and transforming data into a standard format. This ensures that the data types in a dataset are correct (e.g., ensuring numbers are treated as integers or floats, not strings) and that text data is uniform (e.g., converting all text to uppercase). Proper formatting is a critical step before performing any mathematical operations or visualizations.

## 3. Functions Used in the Experiment
This experiment heavily relies on the `pandas` library. Below are the core functions utilized:

* **`pd.DataFrame(data)`**: Converts a dictionary or a 2D array into a structured, tabular data structure called a DataFrame, consisting of rows and columns.
* **`pd.cut(x, bins, labels)`**: The primary function used for binning. It segments and sorts continuous data values into distinct intervals (bins) and assigns a categorical label to each bin.
* **`df.dtypes`**: An attribute that returns the data types of each column in the DataFrame, helping verify if data is stored correctly (e.g., `int64`, `float64`, `object`, `category`).
* **`astype(dtype)`**: Casts a pandas object (like a column) to a specified data type (e.g., converting an integer to a float or a category to a string).
* **`str.upper()`**: A string manipulation method that converts all characters in a text column to uppercase, ensuring uniformity.
* **`sort_values(by='column_name')`**: Sorts the DataFrame in ascending or descending order based on the values in a specified column.
* **`unique()`**: Returns an array of all the distinct, unique values present in a specific column.
* **`value_counts()`**: Returns a count of how many times each unique value appears in a column, which is highly useful for summarizing categorical data.

## 4. Step-by-Step Explanation of the Procedure

### Part A: Product Dataset
* **Data Creation**: A dictionary containing details of electronics (`Product`, `Price`, and `Units_Sold`) is created and converted into a pandas DataFrame.
* **Binning the 'Price' Column**: 
    * **Bins:** `[0, 10000, 30000, 60000]`
    * **Labels:** `['Low', 'Medium', 'High']`
    * *Explanation:* The `pd.cut()` function evaluates the Price. Prices between 0-10,000 become 'Low', 10,001-30,000 become 'Medium', and 30,001-60,000 become 'High'.
* **Binning the 'Units_Sold' Column**:
    * **Bins:** `[0, 30, 60, 100]`
    * **Labels:** `['Low Sales', 'Medium Sales', 'High Sales']`
    * *Explanation:* Similar to price, sales volume is categorized to easily identify high-performing and low-performing products.
* **Data Formatting**:
    * The `Price` column is converted from an integer (`int64`) to a decimal (`float64`) using `.astype(float)`.
    * The `Product` names (e.g., 'Laptop') are standardized to uppercase (e.g., 'LAPTOP') using `.str.upper()`.
* **Sorting and Summarizing**: The DataFrame is sorted by `Price` from lowest to highest, and the unique categories generated during the price binning process are displayed.

### Part B: Food Delivery Orders Dataset
* **Data Creation**: A new dataset simulating food delivery metrics is created (`Order_ID`, `Order_Value`, `Delivery_Time`, `Distance_km`).
* **Multi-Column Binning**:
    * **Delivery_Time**: Segmented into Short, Medium, and Long using intervals `[0, 20, 40, 60]`.
    * **Order_Value**: Segmented into Cheap, Expensive, and Gourmet using intervals `[0, 200, 400, 600]`.
    * **Distance_km**: Segmented into Close, Medium, and Far using intervals `[0, 3, 6, 10]`.
* **Data Formatting**: 
    * `Distance_km` is typecast to a float.
    * The newly created `Price_Category` column is converted from a category data type to a standard string (`object`) using `.astype(str)`.
* **Data Summarization**: The `.value_counts()` function is applied to the `Price_Category` column, revealing that out of all orders, 3 were Expensive, 3 were Gourmet, and 2 were Cheap.

## 5. Conclusion
Through this experiment, continuous numerical data was successfully discretized into meaningful categorical labels using `pd.cut()`. Furthermore, data types were effectively managed and standardized using formatting functions like `astype()` and `str.upper()`. These preprocessing steps are essential for preparing raw data for accurate exploratory data analysis (EDA) and machine learning.
