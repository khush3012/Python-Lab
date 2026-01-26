# Experiment 3: Study of List and Various Operations

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  

## Overview
This project demonstrates the fundamental concepts of Python Lists, a versatile and mutable data structure. The code explores various operations including list creation, indexing, slicing, modification, and the use of built-in methods. Additionally, real-world scenarios such as grocery lists, contact management, and temperature analysis are implemented to showcase practical applications.

## List Operations & Functions Description

Below is a detailed description of the functions and operators used throughout the code:

### 1. Basic List Operations
- **List Creation `[]`**: Lists are defined by enclosing elements within square brackets. They can contain mixed data types (strings, integers, booleans, complex numbers).

- **`len(list)`**: A built-in function that returns the total number of items in a list.
- **`print()`**: Used to output the list or specific elements to the console.

### 2. Accessing Elements
- **Indexing `list[index]`**: Accesses a specific item based on its position.
  - **Positive Indexing:** Starts from `0` for the first item.
  - **Negative Indexing:** Starts from `-1` for the last item.

### 3. Slicing
- **`list[start:end]`**: Extracts a portion of the list from the `start` index up to (but not including) the `end` index.
- **`list[start:end:step]`**: Extracts elements with a specific step count (e.g., skipping every second element).
  - *Example:* `list1[1:5:2]` takes elements from index 1 to 5 with a step of 2.

### 4. Modifying Lists
- **Item Assignment `list[i] = value`**: Changes the value of an item at a specific index.
- **`append(item)`**: Adds a single item to the **end** of the list.
- **`insert(index, item)`**: Adds an item at a **specified position**, shifting subsequent elements to the right.
- **`extend(iterable)`**: Appends elements from another list (or iterable) to the end of the current list.
- **`remove(item)`**: Searches for the first occurrence of the specified item and removes it from the list.

### 5. Utility Operators
- **`in` Operator**: A boolean operator used to check if a specific value exists within a list. Returns `True` or `False`.
- **Repetition `*`**: Repeats the list elements a specified number of times

### 6. Mathematical & Statistical Functions
These functions are used for numerical analysis on lists containing numbers:
- **`max(list)`**: Returns the largest value in the list.
- **`min(list)`**: Returns the smallest value in the list.
- **`sum(list)`**: Calculates the total sum of all numeric elements.
- **Average Calculation**: Performed manually using `sum(list) / len(list)`.

### 7. Sorting
- **`sort()`**: Sorts the elements of the list in ascending order **in-place** (modifies the original list).
  - *Note:* The `sort()` method returns `None`, so it should not be printed directly; print the list after calling `sort()`.
