# Experiment 14: Data Normalization and Data Type Conversion

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 1st April 2026  

---

## 1. Aim
To perform data normalization techniques on numerical variables and convert categorical variables into quantitative variables using Python and the Pandas library.

## 2. Theoretical Background
Before building machine learning models, data must be preprocessed to ensure it is in a uniform and readable format. 


* **Data Normalization:** A technique used to change the values of numeric columns in a dataset to use a common scale, without distorting differences in the ranges of values.
* **Categorical Encoding:** The process of converting categorical (text) data into numerical formats so that mathematical algorithms can process them.

---

## 3. Step-by-Step Code Explanation

### Part A: Data Normalization (Custom Dataset)
In this section, a custom dictionary containing product details (`Price`, `Units_sold`, `Discount`) is converted into a Pandas DataFrame `df` using `pd.DataFrame()`. Three primary normalization techniques are applied:



* **Min-Max Normalization:** * **Concept:** Rescales the data to a fixed range, typically between 0 and 1.
  * **Formula:** `(value - min) / (max - min)`
  * **Execution:** Calculates the minimum (`df['Price'].min()`) and maximum (`df['Price'].max()`) values for the `Price` and `Discount` columns. Applies the formula element-wise to create new columns (`Price_MinMax` and `Dis_MinMax`). A subsequent step demonstrates applying this simultaneously across multiple columns (`cols = ['Price', 'Units_sold', 'Discount']`).
* **Z-Score Normalization (Standardization):**
  * **Concept:** Rescales data so that it has a mean of 0 and a standard deviation of 1. It handles outliers better than Min-Max normalization.
  * **Formula:** `(value - mean) / standard_deviation`
  * **Execution:** Uses `df['Units_sold'].mean()` and `df['Units_sold'].std()` to calculate the respective statistics, applying the formula to create the `Units_Zscore` column.
* **Decimal Scaling:**
  * **Concept:** Normalizes by moving the decimal point of values. The number of decimal points moved depends on the maximum absolute value in the feature.
  * **Execution:** The `Price` column is divided by 100,000 to bring all values below 1.

### Part B: Categorical to Quantitative Conversion (Custom Dataset)
A new custom DataFrame `df1` is created containing categorical features like `Customer_gender`, `Product_category`, and `Payment_method`.



* **Label Encoding:**
  * **Concept:** Assigns a unique integer to each category. Best suited for ordinal data (where there is a natural rank).
  * **Execution:** `LabelEncoder` is imported from `sklearn.preprocessing`. The `.fit_transform()` function is applied to `Customer_gender`, mapping 'Female' to 0 and 'Male' to 1.
* **One-Hot Encoding:**
  * **Concept:** Creates new binary (True/False or 1/0) columns for each unique category in a variable. Best for nominal data (no inherent rank).
  * **Execution:** The Pandas function `pd.get_dummies(df1, columns=['Payment_method'])` creates separate columns for Credit Card and PayPal.
* **Dummy Encoding:**
  * **Concept:** Similar to One-Hot Encoding, but it drops the first created column to avoid multicollinearity (the "dummy variable trap").
  * **Execution:** Executed using `pd.get_dummies()` with the additional argument `drop_first=True` on the `Product_category` column.

### Part C: Operations on the Amazon Dataset
* **Execution:** The dataset `amazon_products_dataset_Expt-14.csv` is loaded using `pd.read_csv()`.
* The exact same normalization logic from Part A is applied to real-world data:
  * **Min-Max Normalization** is applied to `Price`, `Rating`, `Reviews`, and `Units_Sold`.
  * **Z-Score Normalization** is applied to `Price` and `Rating`.
  * **Decimal Scaling** is applied to `Reviews` by dividing by 10,000.

### Part D: Operations on the Student Dataset
* **Execution:** The dataset `Student-Dataset.csv` is loaded.
* The categorical conversion logic from Part B is applied:
  * **Label Encoding** is used on the `Placement_Status` column (mapping "Placed" and "Not Placed" to integers). The `.value_counts()` function confirms the distribution of the newly encoded labels.
  * **One-Hot Encoding** is applied to the `Department` column, creating distinct binary columns for Civil, Computer, ENTC, IT, and Mechanical.
  * **Dummy Encoding** is also applied to `Department` using `drop_first=True`, which drops the first alphabetical category (`Department_Civil`) to reduce redundancy.

---

## 4. Conclusion
Through this experiment, it was observed how different normalization techniques alter the scale and distribution of numerical data. Furthermore, multiple encoding methodologies were successfully implemented using pandas and scikit-learn to transform categorical data into a machine-readable, quantitative format.
