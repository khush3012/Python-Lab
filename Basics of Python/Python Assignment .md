# Python Programming Lab - Assignment 1

## #Program-1: Simple Calculator
### **Aim**
To create a program that performs basic arithmetic operations (addition, subtraction, multiplication, division, and modulus) on two user-provided numbers.

### **Theory**
In Python, the `input()` function is used to capture data from the user as a string. To perform mathematical operations, these strings must be converted into integers using the `int()` function. Arithmetic operators used include:
* `+` (Addition)
* `-` (Subtraction)
* `*` (Multiplication)
* `/` (Division)
* `%` (Modulus - finds the remainder)

### **Steps**
1. Take two inputs from the user.
2. Typecast the inputs from string to integer.
3. Apply the arithmetic operators.
4. Print the results to the console.

### **Conclusion**
The program successfully demonstrates how to handle user input and perform basic arithmetic operations in Python.

---

## #Program-2: Sum and Average of Marks
### **Aim**
To calculate the total sum and the average marks of five students.

### **Theory**
The **Sum** is the total value of all inputs combined. The **Average** (Mean) is calculated by taking the total sum and dividing it by the count of inputs (in this case, 5).

### **Steps**
1. Accept five separate inputs representing marks.
2. Convert all inputs to integers.
3. Sum the five values together.
4. Divide the total sum by 5 to find the average.
5. Display both the total and the average.

### **Conclusion**
The program effectively calculates statistical data from multiple integer inputs.

---

## #Program-3: Area of a Circle
### **Aim**
To find the area of a circle based on a user-defined radius.

### **Theory**
The area of a circle is calculated using the mathematical formula:
$$Area = \pi r^2$$
In this program, we use **3.14** as the constant for $\pi$ and $r$ as the radius provided by the user.

### **Steps**
1. Accept the radius ($r$) as input.
2. Convert the input to an integer.
3. Calculate the area using the formula $3.14 * r * r$.
4. Print the final area.

### **Conclusion**
The program demonstrates the implementation of geometric formulas using Python variables.

---

## #Program-4: Area and Perimeter of a Rectangle
### **Aim**
To compute the area and the perimeter of a rectangle using its length and breadth.

### **Theory**
* **Area** is the total space inside the rectangle: $$Area = Length \times Breadth$$
* **Perimeter** is the total distance around the rectangle: $$Perimeter = 2 \times (Length + Breadth)$$

### **Steps**
1. Input the length ($l$) and breadth ($b$).
2. Convert both values to integers.
3. Calculate Area ($l * b$).
4. Calculate Perimeter ($2 * (l + b)$).
5. Output both results.

### **Conclusion**
The program successfully implements multiple geometric calculations in a single script.
