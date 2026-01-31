# Experiment 5: Sets and Dictionaries in Python

**Name:** Khush  
**PRN:** 25070123062  
**Batch:** A-3  

---

## 1. Python Sets
A set is an unordered collection of items where every element is unique. Sets are written with curly brackets `{}`.

### Core Functions & Methods

`set()`: Converts an iterable (like a list) into a set, removing duplicates.  
`.add(item)`: Adds a single element to the set.  
`.remove(item)`: Removes an element; raises a KeyError if the item is missing.  
 `.discard(item)`: Removes an element; does **not** raise an error if the item is missing.   
 `frozenset()`: Creates an immutable version of a set (cannot be modified).   
 `in`: Membership operator to check if an item exists in the set.   

### Mathematical Set Operations
 **Union** | `\|` |: All elements from both sets.  
 **Intersection** | `&` |: Only elements present in both sets.  
 **Difference** | `-` |: Elements in set A but not in set B.  
 **Symmetric Difference** | `^` |: Elements in either set, but not both.  

---

## 2. Python Dictionaries
Dictionaries are used to store data values in **key:value** pairs. They are ordered and do not allow duplicate keys.

### Core Functions & Methods  
 `dict[key] = value`: Adds a new pair or updates an existing key's value.  
 `.pop(key)`: Removes the specified key and returns its value.  
 `.values()`: Returns a list-like view of all values in the dictionary.  
 `.get(key, default)`: Returns the value for a key; prevents errors if the key is missing.  
 `max(dict, key=dict.get)`: Returns the key with the highest value in the dictionary.  

---

## 3. Key Differences: Sets vs. Dictionaries

| Features | Sets | Dictionaries |
| :--- | :--- | :--- |
| **Data Format** | Single elements `{a, b, c}` | Key-Value pairs `{k: v}` |
| **Accessing** | No indexing; accessed via loops or `in` | Accessed via **Keys** |
| **Duplicates** | No duplicate elements allowed | No duplicate **keys** allowed |
| **Primary Use** | Mathematical operations & uniqueness | Mapping and structured data storage |

---

## 4. Observations & Logic
* **Boolean Handling:** In Python sets, `True` and `1` are treated as the same value, as are `False` and `0`.
* **Ordering:** Sets are unordered
