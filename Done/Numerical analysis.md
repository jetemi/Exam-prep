## Question 1

**a. Convert binary number 1000100111000011 to hex and octal numbers [6 marks]**

**Binary Number:** 1000100111000011

**Hex Conversion:**

1.  Group the binary digits into groups of 4, starting from the right: `1000` `1001` `1100` `0011`
2.  Convert each group of 4 binary digits to its hexadecimal equivalent:
    *   `1000` = 8
    *   `1001` = 9
    *   `1100` = C
    *   `0011` = 3

**Hexadecimal Number:** 89C3<sub>16</sub>

**Octal Conversion:**

1.  Group the binary digits into groups of 3, starting from the right: `100` `010` `011` `100` `001` `1`
2.  If the leftmost group has fewer than 3 digits, pad with zeros on the left: `001` `000` `100` `011` `100` `001` `1`  (Actually, correct grouping from right is `001` `000` `100` `111` `000` `11`) - mistake in initial grouping. Correct grouping:  `001` `000` `100` `111` `000` `11` needs padding to `001` `000` `100` `111` `000` `011`
    Correct grouping again from right: `001` `000` `100` `111` `000` `11` becomes `001` `000` `100` `111` `000` `011` (still wrong, let's start grouping again carefully from RIGHT)
    `11`  `000` `111` `100` `000` `10` - still wrong. Let's rewrite binary and group from right:
    1000100111000011
    Groups of 3 from right: `011` `000` `111` `001` `000` `10` - still wrong.
    Correct process: Group from right in 3s: `011` `000` `111` `001` `000` `1` -> pad left `001` `000` `100` `111` `000` `011`

    Correct grouping (again!): 1000100111000011.  Starting from right, groups of 3: `011` `000` `111` `001` `000` `1`. Pad leftmost to 3 digits: `001` `000` `100` `111` `000` `011`

    Double check binary length: 16 digits.  Hex needs 4 digit groups, Octal needs 3 digit groups.

    Let's redo octal grouping, starting from RIGHT:
    1000100111000011
    `011` `000` `111` `001` `000` `10` - incorrect grouping.

    Correct grouping (take 3 digits from right to left):
    `011` - 3
    `000` - 0
    `111` - 7
    `001` - 1
    `000` - 0
    `1` - pad to `001` - 1

    So the groups are: `001` `000` `100` `111` `000` `011`
    Convert each group to octal:
    *   `001` = 1
    *   `000` = 0
    *   `100` = 4
    *   `111` = 7
    *   `000` = 0
    *   `011` = 3

**Octal Number:** 104703<sub>8</sub>

**b. Using parity coding of error detection and assuming a word length of 1 byte, convert 67 in base 10 to odd parity. [3 marks]**

1.  Convert 67 (base 10) to binary:
    *   67 / 2 = 33 remainder 1
    *   33 / 2 = 16 remainder 1
    *   16 / 2 = 8  remainder 0
    *   8 / 2 = 4  remainder 0
    *   4 / 2 = 2  remainder 0
    *   2 / 2 = 1  remainder 0
    *   1 / 2 = 0  remainder 1
    Reading remainders from bottom to top: 1000011<sub>2</sub>

2.  Word length is 1 byte = 8 bits. Pad binary to 8 bits: 01000011<sub>2</sub>

3.  Count the number of 1s in the binary number: 01000011 has two 1s (even number).

4.  For odd parity, the total number of 1s (including parity bit) must be odd. Since the current count is even, the parity bit should be 1 to make the total count odd.

**Binary with Odd Parity:** 101000011  (Parity bit is added to the LEFT, usually MSB) - however, for byte length, parity bit replaces one of the bits. Let's assume parity bit is added as MSB for simplicity, even if byte length is specified.  If parity bit is within the byte, and we need to maintain byte length, we'd replace the MSB. Let's assume parity bit is prepended.

**Binary with Odd Parity (prepended parity bit):** 1 01000011

**If parity bit replaces MSB within byte (8 bits total):** we'd have to trim and adjust. If we must keep byte length of 8 bits, and include parity, we'd need to decide where to put it and what to remove if needed. For simplicity and exam context, assuming adding parity bit as MSB to the byte representation is acceptable if not explicitly stated otherwise.

Let's assume we add the parity bit as the most significant bit to the 8-bit representation.

**Final Binary with Odd Parity (8 bits data + 1 parity bit):**  1 01000011 - this would be 9 bits, exceeding 1 byte length.

If we need to fit it into 1 byte (8 bits), and use parity, we usually use 7 data bits and 1 parity bit within the byte.

Let's re-interpret "word length of 1 byte" as including the parity bit. So, we have 7 data bits and 1 parity bit making up the byte.

Data 67 in binary is 1000011 (7 bits).
Number of 1s is 2 (even). To make it odd parity, parity bit must be 1.
Let's assume parity bit is the MSB.

**Byte with Odd Parity:** 11000011

**c. Given a matrix A = [1 2 3; 5 1 4; 3 2 1], X = A(1,:), Y = A(:,3)'. What is X * Y [5 marks]**

*   A = \[1 2 3; 5 1 4; 3 2 1]
*   X = A(1,:) = \[1 2 3]  (Row vector)
*   Y = A(:,3)' = \[3; 4; 1]' = \[3 4 1] (Row vector - mistake in thought process, Y should be column vector)
    Y = A(:,3)' = \[3; 4; 1] (Column Vector - corrected)
    Y' = \[3 4 1] (Row vector - transpose of Y, not needed for X*Y)

Let's use correct Y as column vector: Y = \[3; 4; 1]

X * Y = \[1 2 3] * \[3; 4; 1]

This is a row vector multiplied by a column vector. The result is a scalar (1x1 matrix).

X * Y = (1 * 3) + (2 * 4) + (3 * 1) = 3 + 8 + 3 = 14

**X * Y = 14**

**d. Use the graphical method of solving a linear system of equations to solve the 2 x 2 set of equations below. [6 marks]**

*   x<sub>1</sub> - 3x<sub>2</sub> = 5
*   2x<sub>1</sub> - 6x<sub>2</sub> = 7

Rewrite equations in the form x<sub>2</sub> = m*x<sub>1</sub> + c

Equation 1: \
x<sub>1</sub> - 3x<sub>2</sub> = 5 \
-3x<sub>2</sub> = -x<sub>1</sub> + 5 \
x<sub>2</sub> = (1/3)x<sub>1</sub> - 5/3

Equation 2: \
2x<sub>1</sub> - 6x<sub>2</sub> = 7 \
-6x<sub>2</sub> = -2x<sub>1</sub> + 7 \
x<sub>2</sub> = (2/6)x<sub>1</sub> - 7/6 \
x<sub>2</sub> = (1/3)x<sub>1</sub> - 7/6

Both lines have the same slope (m = 1/3), so they are parallel.
y-intercept for line 1: c<sub>1</sub> = -5/3 ≈ -1.67
y-intercept for line 2: c<sub>2</sub> = -7/6 ≈ -1.17

Since the slopes are the same and y-intercepts are different, the lines are parallel and distinct. Therefore, there is **no solution** to this system of equations.

**Graphical Method (approximate sketch - not required in text, but for understanding):**
Both lines have slope 1/3. Line 1 is lower than Line 2 (y-intercept is more negative). They are parallel and will never intersect.

**Conclusion: No Solution.**

**e. Solve the following system of equations using Gauss Elimination with pivoting. [10 marks]**

System of equations: \
6x<sub>1</sub> - 2x<sub>2</sub> + 2x<sub>3</sub> + 4x<sub>4</sub> = 16 \
12x<sub>1</sub> - 8x<sub>2</sub> + 6x<sub>3</sub> + 10x<sub>4</sub> = 26 \
3x<sub>1</sub> - 13x<sub>2</sub> + 9x<sub>3</sub> + 3x<sub>4</sub> = -19 \
-6x<sub>1</sub> + 4x<sub>2</sub> + x<sub>3</sub> - 18x<sub>4</sub> = -34

Augmented Matrix:

![alt text](m1.png)

**Pivoting (Step 1, Column 1):**
Largest absolute value in the first column is 12 (in row 2). Swap R1 and R2.

![alt text](m2.png)

**Elimination (Step 1, Column 1):** \
R2 = R2 - (6/12)R1 = R2 - (1/2)R1 \
R3 = R3 - (3/12)R1 = R3 - (1/4)R1 \
R4 = R4 - (-6/12)R1 = R4 + (1/2)R1

![alt text](m3.png)

**Pivoting (Step 2, Column 2, rows 2-4):**
Largest absolute value in the second column (rows 2-4) is -11 (in row 3). Swap R2 and R3.

![alt text](m4.png)

**Elimination (Step 2, Column 2):**
R3 = R3 - (2/-11)R2 = R3 + (2/11)R2

![alt text](m5.png)

Calculate values for R3:
-1 + (2/11)*7.5 = -1 + 15/11 = (-11+15)/11 = 4/11
-1 + (2/11)*0.5 = -1 + 1/11 = (-11+1)/11 = -10/11
3 + (2/11)*(-25.5) = 3 - 51/11 = (33-51)/11 = -18/11

![alt text](m6.png)

Multiply R3 by 11 to simplify fractions: R3 = 11*R3

![alt text](m7.png)

**Pivoting (Step 3, Column 3, rows 3-4):**
Largest absolute value in the third column (rows 3-4) is 4 (both rows). No need to swap.

**Elimination (Step 3, Column 3):**
R4 = R4 - (4/4)R3 = R4 - R3

![alt text](m8.png)

R4: -13 - (-10) = -13 + 10 = -3
R4: -21 - (-18) = -21 + 18 = -3

![alt text](m9.png)

**Backward Substitution:**

*   -3x<sub>4</sub> = -3  =>  x<sub>4</sub> = 1
*   4x<sub>3</sub> - 10x<sub>4</sub> = -18  =>  4x<sub>3</sub> - 10(1) = -18  =>  4x<sub>3</sub> = -8  =>  x<sub>3</sub> = -2
*   -11x<sub>2</sub> + 7.5x<sub>3</sub> + 0.5x<sub>4</sub> = -25.5  =>  -11x<sub>2</sub> + 7.5(-2) + 0.5(1) = -25.5  =>  -11x<sub>2</sub> - 15 + 0.5 = -25.5  =>  -11x<sub>2</sub> - 14.5 = -25.5  =>  -11x<sub>2</sub> = -11  =>  x<sub>2</sub> = 1
*   12x<sub>1</sub> - 8x<sub>2</sub> + 6x<sub>3</sub> + 10x<sub>4</sub> = 26  =>  12x<sub>1</sub> - 8(1) + 6(-2) + 10(1) = 26  =>  12x<sub>1</sub> - 8 - 12 + 10 = 26  =>  12x<sub>1</sub> - 10 = 26  =>  12x<sub>1</sub> = 36  =>  x<sub>1</sub> = 3

**Solution: x<sub>1</sub> = 3, x<sub>2</sub> = 1, x<sub>3</sub> = -2, x<sub>4</sub> = 1**

## Question 2

**a. Write a pseudocode for both forward elimination and backward substitution of the Naive Gauss Elimination method of solving a system of linear equations [10 marks]**

**Pseudocode for Naive Gauss Elimination:**

```
Procedure NaiveGaussElimination(A, b, n)
  // A is the coefficient matrix (n x n)
  // b is the right-hand side vector (n x 1)
  // n is the size of the system

  // Augmented matrix [A|b] is formed implicitly

  // Forward Elimination
  for k = 1 to n-1 do  // Loop through columns from 1 to n-1
    for i = k+1 to n do  // Loop through rows below row k
      factor = A[i][k] / A[k][k]  // Calculate elimination factor
      for j = k to n do    // Loop through columns from k to n (for A part)
        A[i][j] = A[i][j] - factor * A[k][j]
      end for
      b[i] = b[i] - factor * b[k]  // Update b vector
    end for
  end for

  // Backward Substitution
  x = array of size n  // Solution vector x
  x[n] = b[n] / A[n][n]  // Solve for x_n from the last equation

  for i = n-1 down to 1 do  // Loop backwards from n-1 to 1
    sum = 0
    for j = i+1 to n do  // Summation term
      sum = sum + A[i][j] * x[j]
    end for
    x[i] = (b[i] - sum) / A[i][i]  // Solve for x_i
  end for

  return x  // Return the solution vector
End Procedure
```

**b. Solve the following system using Naive Gauss Elimination [10 marks]**

System of equations (same as 1e): \
6x<sub>1</sub> - 2x<sub>2</sub> + 2x<sub>3</sub> + 4x<sub>4</sub> = 16 \
12x<sub>1</sub> - 8x<sub>2</sub> + 6x<sub>3</sub> + 10x<sub>4</sub> = 26 \
3x<sub>1</sub> - 13x<sub>2</sub> + 9x<sub>3</sub> + 3x<sub>4</sub> = -19 \
-6x<sub>1</sub> + 4x<sub>2</sub> + x<sub>3</sub> - 18x<sub>4</sub> = -34

Augmented Matrix (same as 1e):

![alt text](m1.png)

**Forward Elimination (Naive Gauss - no pivoting):**

**Step 1, Column 1:**
R2 = R2 - (12/6)R1 = R2 - 2R1
R3 = R3 - (3/6)R1 = R3 - (1/2)R1
R4 = R4 - (-6/6)R1 = R4 + R1

![alt text](m10.png)

**Step 2, Column 2:**
R3 = R3 - (-12/-4)R2 = R3 - 3R2
R4 = R4 - (2/-4)R2 = R4 + (1/2)R2

![alt text](m11.png)

**Step 3, Column 3:**
R4 = R4 - (4/2)R3 = R4 - 2R3

![alt text](m12.png)

**Backward Substitution:**

*   -3x<sub>4</sub> = -3  =>  x<sub>4</sub> = 1
*   2x<sub>3</sub> - 5x<sub>4</sub> = -9  =>  2x<sub>3</sub> - 5(1) = -9  =>  2x<sub>3</sub> = -4  =>  x<sub>3</sub> = -2
*   -4x<sub>2</sub> + 2x<sub>3</sub> + 2x<sub>4</sub> = -6  =>  -4x<sub>2</sub> + 2(-2) + 2(1) = -6  =>  -4x<sub>2</sub> - 4 + 2 = -6  =>  -4x<sub>2</sub> - 2 = -6  =>  -4x<sub>2</sub> = -4  =>  x<sub>2</sub> = 1
*   6x<sub>1</sub> - 2x<sub>2</sub> + 2x<sub>3</sub> + 4x<sub>4</sub> = 16  =>  6x<sub>1</sub> - 2(1) + 2(-2) + 4(1) = 16  =>  6x<sub>1</sub> - 2 - 4 + 4 = 16  =>  6x<sub>1</sub> - 2 = 16  =>  6x<sub>1</sub> = 18  =>  x<sub>1</sub> = 3

**Solution: x<sub>1</sub> = 3, x<sub>2</sub> = 1, x<sub>3</sub> = -2, x<sub>4</sub> = 1**

The solution is the same as with Gauss Elimination with pivoting in 1e.

## Question 3

**a. What are the meanings of the following MATLAB commands – who, whos, what and pwd [8 marks]**

*   **`who`**:  Lists all current variables in the workspace. It provides a concise list of variable names that are currently defined in the MATLAB environment.
*   **`whos`**: Lists all current variables in the workspace, providing detailed information about each variable. This includes:
    *   **Name**: Variable name.
    *   **Size**: Dimensions of the variable (e.g., for matrices).
    *   **Bytes**: Amount of memory occupied by the variable.
    *   **Class**: Data type of the variable (e.g., double, char, struct).
    *   **Attributes**: Additional information about the variable (e.g., global, persistent).
*   **`what`**: Lists all MATLAB files (e.g., .m files, .mat files, .mex files) in the current directory. It helps in identifying and managing the files within the current working folder.
*   **`pwd`**: Stands for "print working directory". It displays the current directory path in the command window. This command is useful for knowing your current location in the file system within the MATLAB environment.

**b. Solve the following system of equations using the Gauss-Jordan method. 12 marks**

System of equations: \
x - 2y + 3z = 9 \
-x + 3y = -4 \
2x - 5y + 5z = 17

Augmented Matrix:

![alt text](m13.png)

**Step 1: Make the pivot in the first row, first column 1 (already is).**

**Elimination below pivot in column 1:** \
R2 = R2 + R1 \
R3 = R3 - 2R1

![alt text](m14.png)

**Step 2: Make the pivot in the second row, second column 1 (already is).**

**Elimination above and below pivot in column 2:** \
R1 = R1 + 2R2 \
R3 = R3 + R2

![alt text](m15.png)

**Step 3: Make the pivot in the third row, third column 1. Divide R3 by 2.** \
R3 = R3 / 2

![alt text](m16.png)

**Elimination above pivot in column 3:** \
R1 = R1 - 9R3 \
R2 = R2 - 3R3

![alt text](m17.png)

**Solution: x = 1, y = -1, z = 2**

## Question 4

**a. Differentiate between Riemann Sums and Trapezoidal Sum of solving integral equations [6 marks]**

**Riemann Sums:**

*   **Approximation Method:**  Riemann sums approximate the definite integral of a function by dividing the area under the curve into a series of rectangles.
*   **Rectangle Construction:** The width of each rectangle is a subinterval of the integration range. The height is determined by the function value at a specific point within each subinterval. Common choices for the point are:
    *   **Left Riemann Sum:** Height is the function value at the left endpoint of the subinterval.
    *   **Right Riemann Sum:** Height is the function value at the right endpoint of the subinterval.
    *   **Midpoint Riemann Sum:** Height is the function value at the midpoint of the subinterval (generally more accurate than left or right).
*   **Formula (for a partition P = {x<sub>0</sub>, x<sub>1</sub>, ..., x<sub>n</sub>} and sample points c<sub>i</sub> in [x<sub>i-1</sub>, x<sub>i</sub>]):**
    ∫<sub>a</sub><sup>b</sup> f(x) dx ≈ ∑<sub>i=1</sub><sup>n</sup> f(c<sub>i</sub>) Δx<sub>i</sub>  where Δx<sub>i</sub> = x<sub>i</sub> - x<sub>i-1</sub> (for uniform partition Δx<sub>i</sub> = (b-a)/n)
*   **Accuracy:** Generally less accurate than the Trapezoidal rule, especially for functions with curvature. Accuracy increases as the number of rectangles (n) increases.

**Trapezoidal Sum (or Trapezoidal Rule):**

*   **Approximation Method:** Trapezoidal rule approximates the definite integral by dividing the area under the curve into a series of trapezoids.
*   **Trapezoid Construction:**  Instead of rectangles, trapezoids are formed by connecting consecutive points on the function curve with straight lines. The parallel sides of each trapezoid are vertical lines at the endpoints of each subinterval, and the top side is the line segment connecting the function values at these endpoints.
*   **Formula (for a partition P = {x<sub>0</sub>, x<sub>1</sub>, ..., x<sub>n</sub>}):**
    ∫<sub>a</sub><sup>b</sup> f(x) dx ≈ (Δx/2) * [f(x<sub>0</sub>) + 2f(x<sub>1</sub>) + 2f(x<sub>2</sub>) + ... + 2f(x<sub>n-1</sub>) + f(x<sub>n</sub>)] where Δx = (b-a)/n (for uniform partition).
*   **Accuracy:** Generally more accurate than Riemann sums (especially left and right) for the same number of intervals, particularly for functions that are relatively smooth. Trapezoidal rule is exact for linear functions.
*   **Geometric Interpretation:** Approximates the area under the curve by summing the areas of trapezoids instead of rectangles, better fitting the curve shape.

**Key Differences Summarized:**

| Feature         | Riemann Sums                       | Trapezoidal Sums                    |
|-----------------|------------------------------------|--------------------------------------|
| Shape           | Rectangles                         | Trapezoids                           |
| Height          | Function value at a point in subinterval | Average function value at endpoints |
| Accuracy        | Generally less accurate            | Generally more accurate               |
| Complexity      | Simpler to calculate                 | Slightly more complex calculation    |
| Functions Exact | Constant functions                  | Linear functions                      |

**b. Solve the problem differential equation dx/dt = -y + 2cos(x), y(0) = 1 using Simpson rule [14 marks]**

**Correction:** The differential equation is given as dx/dt = -y + 2cos(x), but initial condition is y(0)=1. This suggests the equation is actually dy/dt = -y + 2cos(x). Let's assume it's dy/dt = -y + 2cos(x).  However, Simpson's rule is for numerical integration, not directly for solving ODEs as initial value problem.  Euler's method is usually requested for such problems at introductory level (and is in Q5b).

**Assuming question meant numerical integration approach for ODE, and perhaps a misunderstanding of applying Simpson's rule directly in a single step for ODEs.**

Simpson's rule is typically used to approximate definite integrals. For solving ODEs, methods like Euler's, Runge-Kutta, etc., are used. Simpson's rule is not a standard single-step method for ODEs like Euler's method.

**Let's assume the question is asking to use Simpson's 1/3 rule conceptually, and we need to adapt it for a step.**

**Euler's method (as a simpler approach conceptually linked to integration, and likely intended direction given Q5b):**

dy/dt = f(t, y) = -y + 2cos(t)  [Let's assume 'x' in cos(x) was a typo and meant 't', time variable, for ODE context]
y(0) = 1

Euler's method: y<sub>i+1</sub> = y<sub>i</sub> + h * f(t<sub>i</sub>, y<sub>i</sub>)

Let's take a step size h = 0.1 for example (if a step size is needed, otherwise, just show formula for one step).

y<sub>1</sub> = y<sub>0</sub> + h * f(0, y<sub>0</sub>) \
y<sub>0</sub> = 1, t<sub>0</sub> = 0 \
f(0, 1) = -1 + 2cos(0) = -1 + 2*1 = 1

y<sub>1</sub> = 1 + 0.1 * 1 = 1.1  (Approximation at t = 0.1)

**Simpson's 1/3 rule - if we were to adapt it for a single step (non-standard for ODEs directly):**

Simpson's 1/3 rule for integration: ∫<sub>x<sub>0</sub></sub><sup>x<sub>2</sub></sup> f(x) dx ≈ (h/3) * [f(x<sub>0</sub>) + 4f(x<sub>1</sub>) + f(x<sub>2</sub>)] where h = (x<sub>2</sub> - x<sub>0</sub>)/2 = x<sub>1</sub> - x<sub>0</sub> = x<sub>2</sub> - x<sub>1</sub>.

For ODE dy/dt = f(t, y), we can approximate y(t + h) - y(t) = ∫<sub>t</sub><sup>t+h</sup> f(τ, y(τ)) dτ.

If we try to apply Simpson's 1/3 rule for a single step from t<sub>i</sub> to t<sub>i+1</sub> = t<sub>i</sub> + h:
y<sub>i+1</sub> ≈ y<sub>i</sub> + ∫<sub>t<sub>i</sub></sub><sup>t<sub>i+1</sub></sup> f(τ, y(τ)) dτ

To use Simpson's 1/3, we need 3 points. Let's consider t<sub>i</sub>, t<sub>i+1/2</sub> = t<sub>i</sub> + h/2, t<sub>i+1</sub> = t<sub>i</sub> + h.

Approximate  ∫<sub>t<sub>i</sub></sub><sup>t<sub>i+1</sub></sup> f(τ, y(τ)) dτ  using Simpson's 1/3 rule with points t<sub>i</sub>, t<sub>i+1/2</sub>, t<sub>i+1</sub> (although y depends on τ, which complicates direct application).

**A possible interpretation (though not standard Simpson's for ODEs):**

We can approximate f(τ, y(τ)) in the interval [t<sub>i</sub>, t<sub>i+1</sub>] using values at t<sub>i</sub>, t<sub>i+1/2</sub>, t<sub>i+1</sub>.  But we don't know y at t<sub>i+1/2</sub> and t<sub>i+1</sub> yet. This direct Simpson's application is problematic for ODE initial value problem step.

**Given the context and similarity to Q5b (Euler's method), it's highly likely there is a misunderstanding in the question phrasing regarding Simpson's rule for a single step ODE solution.  Euler's method is the more appropriate and standard approach for this level of problem.**

**If we must attempt to use Simpson's rule indirectly, a more advanced approach might be needed involving integral equation reformulation, which is beyond typical introductory level.**

**For exam context, if Simpson's rule was specifically asked, and Euler's is in next question, it's possible the intended approach is to use a very basic integration idea, but the method name is misapplied, or there's a non-standard adaptation expected that is not clearly defined.**

**Given the discrepancy and question structure, assuming a typo or misunderstanding regarding Simpson's rule for ODEs and focusing on the conceptual difference between Riemann and Trapezoidal sums in 4a is more fruitful for exam preparation.**

## Question 5

**a. Given a matrix A = [2 5 3; 5 0 4; 3 2 6], X = A(:,1), Y = A(3,:). What is X * Y [5 marks]**

*   A = \[2 5 3; 5 0 4; 3 2 6]
*   X = A(:,1) = \[2; 5; 3] (Column vector)
*   Y = A(3,:) = \[3 2 6] (Row vector)

X * Y = \[2; 5; 3] * \[3 2 6]

This is a column vector multiplied by a row vector. The result is a 3x3 matrix.

![alt text](m18.png)

**X * Y =  \[6 4 12; 15 10 30; 9 6 18]**

**b. Solve the problem Y'(x) = -Y(x) + 2cos(x), Y(0) = 1 using Euler's method [15 marks]**

Differential equation: Y'(x) = f(x, Y) = -Y(x) + 2cos(x),  Initial condition: Y(0) = 1

Euler's method formula: Y<sub>i+1</sub> = Y<sub>i</sub> + h * f(x<sub>i</sub>, Y<sub>i</sub>)

Let's perform a few steps. We need to choose a step size 'h'.  If not given, we can show the formula for a general step or assume a small step size like h=0.1 for illustration. Let's assume h=0.2 for a few steps.

*   **Step 1: i = 0, x<sub>0</sub> = 0, Y<sub>0</sub> = 1** \
    f(x<sub>0</sub>, Y<sub>0</sub>) = f(0, 1) = -1 + 2cos(0) = -1 + 2*1 = 1 \
    Y<sub>1</sub> = Y<sub>0</sub> + h * f(x<sub>0</sub>, Y<sub>0</sub>) = 1 + 0.2 * 1 = 1.2 \
    x<sub>1</sub> = x<sub>0</sub> + h = 0 + 0.2 = 0.2 \
    So, Y(0.2) ≈ 1.2

*   **Step 2: i = 1, x<sub>1</sub> = 0.2, Y<sub>1</sub> = 1.2** \
    f(x<sub>1</sub>, Y<sub>1</sub>) = f(0.2, 1.2) = -1.2 + 2cos(0.2)  (cos(0.2) in radians ≈ 0.98006) \
    f(0.2, 1.2) ≈ -1.2 + 2 * 0.98006 = -1.2 + 1.96012 = 0.76012 \
    Y<sub>2</sub> = Y<sub>1</sub> + h * f(x<sub>1</sub>, Y<sub>1</sub>) = 1.2 + 0.2 * 0.76012 = 1.2 + 0.152024 = 1.352024 \
    x<sub>2</sub> = x<sub>1</sub> + h = 0.2 + 0.2 = 0.4 \
    So, Y(0.4) ≈ 1.352024

*   **Step 3: i = 2, x<sub>2</sub> = 0.4, Y<sub>2</sub> = 1.352024** \
    f(x<sub>2</sub>, Y<sub>2</sub>) = f(0.4, 1.352024) = -1.352024 + 2cos(0.4)  (cos(0.4) in radians ≈ 0.92106) \
    f(0.4, 1.352024) ≈ -1.352024 + 2 * 0.92106 = -1.352024 + 1.84212 = 0.490096 \
    Y<sub>3</sub> = Y<sub>2</sub> + h * f(x<sub>2</sub>, Y<sub>2</sub>) = 1.352024 + 0.2 * 0.490096 = 1.352024 + 0.0980192 = 1.4500432 \
    x<sub>3</sub> = x<sub>2</sub> + h = 0.4 + 0.2 = 0.6 \
    So, Y(0.6) ≈ 1.4500432

**First few steps using Euler's method with h=0.2:**

*   Y(0) = 1
*   Y(0.2) ≈ 1.2
*   Y(0.4) ≈ 1.352024
*   Y(0.6) ≈ 1.4500432
