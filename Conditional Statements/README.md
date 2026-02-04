# Experiment 6: Study of Conditional Statements in Python

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  

---

## Objectives
* To understand the syntax of `if`, `elif`, and `else` in Python.
* To implement logical operators (`and`, `or`, `not`) within conditions.
* To solve real-world problems like tax calculation, salary slips, and date validation.

---

##   Algorithms

### 1. Number Nature (Positive/Negative/Zero)
1. Start.
2. Input a number n.
3. Check if n > 0: Print "Positive".
4. Check if n < 0: Print "Negative".
5. Otherwise: Print "Zero".
6. Stop.

### 2. Odd or Even
1. Start.
2. Input number n.
3. If n \pmod 2 = 0: Print "Even".
4. Else: Print "Odd".
5. Stop.

### 3. Greater of Two Numbers
1. Start.
2. Input num1 and num2.
3. If num1 > num2: Print num1 is greater.
4. Else: Print num2 is greater.
5. Stop.

### 4. Largest of Three Numbers
1. Start.
2. Input num1, num2, num3.
3. Compare using logical `AND`: 
    * If (num1 > num2) and (num1 > num3), num1 is largest.
    * If (num2 > num1) and (num2 > num3),$num2 is largest.
    * Else num3 is largest.
4. Stop.

### 5. Grade & Average Calculation
1. Start.
2. Input marks for 5 subjects.
3. Calculate Average = \frac{\sum Marks}{5}.
4. Use `if-elif` ladder to assign grades (O, A+, A, B+, B, or Fail) based on the Average value.
5. Stop.

### 6. Leap Year Check
1. Start.
2. Input year.
3. If (year \% 4 == 0 \text{ and } year \% 100 != 0) \text{ or } (year \% 400 == 0):
    * Print "Leap Year".
4. Else: Print "Not a Leap Year".
5. Stop.

### 7. Date Validation & Increment
1. Start.
2. Input date string, split into DD,MM, YY.
3. Validate M (1-12) and D based on the specific month and leap year rules.
4. If valid, check if D is the last day of the month.
    * If yes: Set D=1, increment M. (If M>12, set M=1, increment Y).
    * If no: Increment D.
5. Stop.

### 8. Gross Salary Calculation
1. Start.
2. Input Basic.
3. If Basic = 10,000: HRA=20\%, DA=80\%.
4. Else if Basic = 20,000: HRA=25\%, DA=90\%.
5. Else: HRA=30\%, DA=95\%.
6. Calculate Gross = Basic + HRA + DA.
7. Stop.

### 9. Income Tax Calculation
1. Start.
2. Input Income.
3. Use conditional slabs:
    * 0\% \text{ for } < 2.5L.
    * 5\% \text{ for } 2.5L - 5L.
    * 20\% \text{ for } 5L - 10L.
    * 30\% \text{ for } > 10L.
4. Stop.

---

## Conclusion

Through this experiment, we have successfully implemented and analyzed various **conditional structures** in Python, ranging from simple `if-else` blocks to complex `nested conditions` and `if-elif-else` ladders. 

---
