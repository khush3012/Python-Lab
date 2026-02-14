# Experiment 7: Loops in Python

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 06/02/2026

---

## 1. Theory & Concepts

### While Loop
The `while` loop is a control flow statement that allows code to be executed repeatedly based on a given Boolean condition. The `while` loop can be thought of as a repeating `if` statement.

* **Usage:** It is typically used when the number of iterations is not known beforehand and depends on a dynamic condition (e.g., waiting for user input, mathematical convergence).
* **Syntax:**
    ```python
    while condition:
        statement(s)
    ```

###  For Loop
The `for` loop in Python is used for iterating over a sequence (such as a list, tuple, dictionary, set, or string). Unlike `while`, the `for` loop is generally used when the number of iterations is known or finite.

* **Usage:** Iterating through items in a collection or running a block of code a specific number of times using the `range()` function.
* **Syntax:**
    ```python
    for variable in sequence:
        statement(s)
    ```

###  Nested Loops
A nested loop is a loop inside the body of another loop. The "inner loop" will finish all of its iterations for each single iteration of the "outer loop".

* **Usage:** Commonly used for working with multi-dimensional data structures like matrices (lists of lists) or generating complex patterns.

###  Loop Control Statements
* **Break:** The `break` statement terminates the loop containing it. Control of the program flows to the statement immediately after the body of the loop.
* **Continue:** The `continue` statement skips the rest of the code inside a loop for the current iteration only. The loop does not terminate but continues on with the next iteration.

---

## 2. Algorithms

Below are the algorithms for the specific codes implemented in this experiment.

### Program 1: Print numbers 1 to 5 (While Loop)
1. Initialize a variable `i` to 1.
2. Check if `i` is less than or equal to 5.
3. If true, print the value of `i`.
4. Increment `i` by 1.
5. Repeat steps 2-4 until the condition becomes false.

### Program 2: Print numbers 1 to N (User Input)
1. Accept integer input `n` from the user.
2. Initialize counter `i` to 1.
3. While `i` is less than or equal to `n`:
    * Print `i` (staying on the same line).
    * Increment `i` by 1.
4. End loop.

### Program 3: Factorial of a number
1. Accept integer `n` from the user.
2. Initialize `fact` to 1.
3. While `n` is greater than or equal to 1:
    * Multiply `fact` by `n` (`fact = fact * n`).
    * Decrement `n` by 1.
4. Print the final value of `fact`.

### Program 4: Fibonacci Series
1. Accept `n` (number of terms) from the user.
2. Initialize variables: `a = 0`, `b = 1`, and counter `i = 0`.
3. While `i` is less than `n`:
    * Print `a`.
    * Calculate next term `c = a + b`.
    * Update `a = b` and `b = c`.
    * Increment `i` by 1.

### Program 5: Reverse a Number
1. Accept integer `num` from the user.
2. Initialize `rev` to 0.
3. While `num` is greater than 0:
    * Extract the last digit: `digit = num % 10`.
    * Update `rev`: `rev = rev * 10 + digit`.
    * Remove the last digit from `num` (integer division by 10).
4. Print `rev`.

### Program 6: Check Palindrome (String method)
1. Accept a string input `string`.
2. Create a reversed version of the string `rev` using slicing `[::-1]`.
3. Compare `string` with `rev`.
4. If they are equal, print "Palindrome".
5. Else, print "Not Palindrome".

### Program 7: Count digits in a number
1. Accept integer `num`.
2. Initialize `count` to 0.
3. While `num` is greater than 0:
    * Increment `count` by 1.
    * Remove the last digit of `num` (integer division by 10).
4. Print `count`.

### Program 8: Break Statement (Exit when i=3)
1. Initialize `i = 1`.
2. Start a while loop with condition `i < 6`.
3. Print `i`.
4. Check if `i` equals 3.
    * If true, execute `break` (exit loop).
5. Increment `i` by 1.
6. Repeat.

### Program 9: Search element in list (Linear Search)
1. Define a list of PRN strings `prn_nos`.
2. Accept PRN to search from the user.
3. Initialize index `i = 0` and get list length `length`.
4. While `i < length`:
    * Check if `prn_nos[i]` equals input PRN.
    * If true, print "Found" and index, then break.
    * Increment `i`.
5. If the loop completes without breaking (using `else` block of `while`), print "Not found".

### Program 10: Continue Statement (Skip 5)
1. Initialize `i = 1`.
2. While `i <= 10`:
    * Check if `i` equals 5.
    * If true, increment `i` and execute `continue` (skip printing).
    * Print `i`.
    * Increment `i`.

### Program 11: Print Odd Numbers (Skip Even)
1. Initialize `i = 1`.
2. While `i < 10`:
    * Check if `i` is even (`i % 2 == 0`).
    * If true, increment `i` and `continue`.
    * Print `i`.
    * Increment `i`.

### Program 12: Print 1 to 6 (For Loop)
1. Iterate variable `i` in the range 1 to 6 (exclusive of 7).
2. Print `i` in the same line.

### Program 13: Print Even Numbers 1 to 10
1. Iterate variable `x` in the range starting at 2, ending at 11, with a step of 2.
2. Print `x`.

### Program 14: Sum of first N numbers
1. Accept integer `n`.
2. Initialize `total = 0`.
3. Iterate `i` from 1 to `n` (inclusive):
    * Add `i` to `total`.
4. Print `total`.

### Program 15: Nested For Loop (Coordinates)
1. Start outer loop `i` from 1 to 3.
2. Start inner loop `j` from 1 to 3.
3. Print pair `(i, j)`.
4. End inner loop.
5. End outer loop.

### Program 16: 3x3 Matrix Display
1. Define a 3x3 matrix `A` (list of lists).
2. Start outer loop `i` from 0 to 2 (rows).
3. Start inner loop `j` from 0 to 2 (columns).
4. Print `A[i][j]` followed by a space.
5. After the inner loop finishes (end of a row), print a newline.

### Program 17: Matrix Multiplication
1. Define 3x3 matrices `A` and `B`.
2. Initialize a 3x3 zero matrix `Result`.
3. Start loop `i` (0 to 2) for rows of `A`.
4. Start loop `j` (0 to 2) for columns of `B`.
5. Start loop `k` (0 to 2) for dot product calculation.
    * `Result[i][j] += A[i][k] * B[k][j]`.
6. Print the `Result` matrix row by row.

### Program 18: Combinations of 3 Digits
1. Accept three string inputs.
2. Store them in a list `d`.
3. Use three nested loops (`i`, `j`, `k`) iterating from 0 to 2.
4. Check condition: If indices point to unique values (values are distinct), print the combination `d[i], d[j], d[k]`.

### Program 19: Armstrong Number Check
1. Accept number as string `num`.
2. Calculate length of string.
3. Initialize `sum = 0`.
4. Iterate `i` through each digit in `num`:
    * Convert digit to integer.
    * Raise digit to the power of length.
    * Add result to `sum`.
5. If `sum` equals the original integer `num`, print "Armstrong Number".
6. Else, print "Not an Armstrong Number".

### Program 20: Prime Number Check
1. Accept integer `num`.
2. Iterate `i` from 2 up to `num - 1`.
3. Check if `num % i == 0`.
    * If true, the number is not prime; break the loop.
4. If the loop completes without finding a divisor, the number is Prime.

### Program 21: Inverted Pyramid Pattern
1. Set `n = 5`.
2. Iterate `i` from 0 to `n-1`.
3. Print `i` spaces followed by `(n-i)` occurrences of the symbol `$`.

### Program 22: Pyramid Pattern
1. Set `n = 5`.
2. Iterate `i` from 0 to `n-1`.
3. Print `(n-i)` spaces followed by `i` occurrences of the symbol `$`.

### Program 23: Right Angled Triangle Pattern
1. Set `n = 5`.
2. Iterate `i` from 5 down to 1 (step -1).
3. Print `(n-i)` asterisks `*` (Note: based on output logic provided in code).

### Program 24: Floyd's Triangle
1. Accept number of rows `n`.
2. Initialize `number = 1`.
3. Outer loop `i` from 1 to `n`.
4. Inner loop `j` from 1 to `i`.
    * Print `number`.
    * Increment `number`.
5. Print newline after inner loop.

### Program 25: Number Pattern (1, 22, 333...)
1. Iterate `i` from 1 to 5.
2. Print `i` as a string, repeated `i` times (e.g., if `i` is 3, print "333").
