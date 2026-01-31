# Tuples

**Name:** Khush  
**PRN:** 25070123062  
**Batch:** A-3  

---

## Description
This experiment explores the properties, syntax, and practical applications of Tuples in Python. A tuple is a collection which is ordered and immutable, making it ideal for storing data that should not change throughout the execution of a program.

## Functions and Operations Demonstrated

### 1. Basic Operations
* **Creation & Access:** Defining tuples using parentheses `()` and accessing items via index numbers.
* **Immutability Handling:** Demonstrating that tuples cannot be changed directly. To "modify" a tuple, we use concatenation:
  - `tuple1 + tuple2`
  - `tuple[0:n] + ("New Element",) + tuple[n+1:]`

### 2. Slicing Techniques
The experiment covers advanced slicing using the `[start:stop:step]` syntax:
* **Positive Slicing:** Extracting sub-sections of a tuple.
* **Negative Slicing:** Accessing elements relative to the end of the tuple.
* **Step Slicing:** Skipping elements or reversing order using a negative step.



### 3. Built-in Functions of Tuples
 `tuple.count(x)` Returns the number of times `x` appears in the tuple.   
 `len(tuple)`  Returns the total number of items in the tuple. 


* **Tuple Unpacking:** Assigning tuple values directly to multiple variables (e.g., `subject, marks, grade = result`).
* **Conditional Logic:** Integrating tuples with `if` statements to filter data (e.g., checking for "Distinction" or attendance thresholds).


