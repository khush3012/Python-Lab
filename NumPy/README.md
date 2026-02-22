# Experiment 8: Tools for Exploratory Data Analysis (EDA) - Study of NumPy

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** Entc - A3  
**Date:** 18/02/2026  

---

## 1. Introduction and Objective
The objective of this experiment is to explore and understand **NumPy** (Numerical Python), a fundamental library in Python used for Exploratory Data Analysis (EDA) and scientific computing.

**Why NumPy?**
* **Performance:** It executes operations significantly faster than standard Python lists.
* **Utility:** It is strictly designed for high-performance numerical computation.
* **Foundation:** It serves as the foundational base for other essential data science libraries, such as Pandas.

---

## 2. Array Declaration and Attributes
This section demonstrates how to create NumPy arrays and inspect their foundational properties.

* `import numpy as np`: This imports the NumPy library into the environment, using the standard alias `np`.
* `np.array()`: Used to initialize arrays. In this experiment, a 1-Dimensional array `a` `[10, 20, 30, 40]` and a 2-Dimensional array `b` `[[1, 2, 3], [4, 5, 6]]` were created.
* `.ndim`: An attribute that returns the number of dimensions of the array. Array `a` returns 1 (1D), and array `b` returns 2 (2D).
* `.shape`: Returns a tuple indicating the size of the array in each dimension. Array `a` has a shape of `(4,)` meaning 4 elements in a single dimension, while array `b` has a shape of `(2, 3)` meaning 2 rows and 3 columns.
* `.dtype`: Returns the data type of the elements stored in the array. For both `a` and `b`, the elements are automatically assigned the 64-bit integer type (`int64`).

---

## 3. In-Built Array Initialization Functions
NumPy provides robust functions to quickly generate standard matrices without manually typing the values.

* `np.zeros((row, col))`: Generates an array of the specified shape filled entirely with zeros (e.g., a 2x3 matrix of `0.`).
* `np.ones((row, col))`: Generates an array of the specified shape filled entirely with ones (e.g., a 3x4 matrix of `1.`).
* `np.eye(n)`: Creates an identity matrix of size `n x n` (e.g., a 4x4 matrix), where all diagonal elements are `1.` and all other elements are `0.`.

---

## 4. Sequence Generation
These functions are used to generate arrays with evenly distributed values.

* `np.arange(start, stop, step)`: Returns an array with evenly spaced values within a specified interval. For example, `np.arange(1, 30, 4)` starts at 1, takes steps of 4, and stops before 30, resulting in `[1, 5, 9, 13, 17, 21, 25, 29]`.
* `np.linspace(start, stop, num)`: Returns an array of exactly `num` evenly spaced numbers calculated over the interval `[start, stop]`. For instance, `np.linspace(0, 1, 5)` divides the range 0 to 1 into 5 precisely equal parts.

---

## 5. Arithmetic Operations (Broadcasting)
NumPy allows for direct scalar arithmetic operations on arrays, known as broadcasting.

* `b * 2`: Multiplies every individual element in the 2D array `b` by 2.
* `a + 5`: Adds 5 to every individual element in the 1D array `a`.

---

## 6. Statistical and Aggregation Functions
These in-built mathematical functions are essential for summarizing data during Exploratory Data Analysis.

* `np.max()` / `np.min()`: Returns the maximum and minimum values present in the array, respectively.
* `np.sum()`: Calculates the aggregate sum of all elements within the given array.
* `np.mean()`: Calculates the arithmetic average of the elements in the array.
* `np.median()`: Finds the middle value of the sorted array.

> **💡 EDA Note on Mean vs. Median:** > Comparing the mean and median is highly useful for data cleaning. If the mean and median are nearly identical, the data is relatively clean and symmetrical. If there is a huge difference, it indicates the presence of outliers. In the presence of high-variance outliers, the median is always the more reliable metric to use.

---

## 7. Conclusion
Through this experiment, various capabilities of the NumPy library were explored. The use of basic array creation, shape manipulation, built-in matrix generation, broadcasting, and foundational statistical functions was successfully practiced. These operations form the core of numerical processing required for effective Exploratory Data Analysis.
