Here's a breakdown of the past questions:

**Question 1**

*   **a.** Two lengths X and Y are measured to be approximately X ~ 3.32 and Y ~ 5.39, the symbol ~ representing approximate equality. Compute approximations to X + Y, X + (.1)Y and X + (.01)Y by "three digit addition".
    *   **X + Y:** 3.32 + 5.39 = 8.71
    *   **X + (0.1)Y:** 3.32 + (0.1)(5.39) = 3.32 + 0.539 = 3.859  (Rounded to 3 digits: 3.86)
    *   **X + (0.01)Y:** 3.32 + (0.01)(5.39) = 3.32 + 0.0539 = 3.3739 (Rounded to 3 digits: 3.37)
*   **b.** What is the largest non-negative integer that stores integers as unsigned bit words.
    *   For an unsigned bit word, you need the number of bits. You can calculate the maximum value the bit word can hold with the following formula 2^n -1, where n is the number of bits.
    *   In the absence of a specification, this cannot be calculated
*   **c.** Differentiate between absolute and relative error.
    *   **Absolute Error:** The difference between the approximate value and the true value. It has the same units as the quantity being measured.
        *   Formula: |Approximate Value - True Value|
    *   **Relative Error:** The absolute error divided by the true value. It is usually expressed as a percentage and provides a better sense of the error's significance.
        *   Formula: |Approximate Value - True Value| / |True Value|
*   **d.** The relative error in an approximate solution is 0.004%. What is the number of significant digits in the solution that can be trusted?
    *   To determine the number of significant digits that can be trusted, use this formula
    *   number of correct significant digits = -log10 (relative error)
    *   number of correct significant digits = -log10(0.00004) = -(-4.397) = 4.397
    *   Therefore, the solution can have 4 significant digits that can be trusted
*   **e.** What is the decimal equivalent of the binary number 110010₂?
    *   110010₂ = (1 \* 2⁵) + (1 \* 2⁴) + (0 \* 2³) + (0 \* 2²) + (1 \* 2¹) + (0 \* 2⁰)
    *   = 32 + 16 + 0 + 0 + 2 + 0
    *   = 50₁₀
*   **f.** What is the binary equivalent of the decimal number 25.375₁₀?
    *   **Integer Part (25):** Convert to binary.
        *   25 / 2 = 12 remainder 1
        *   12 / 2 = 6 remainder 0
        *   6 / 2 = 3 remainder 0
        *   3 / 2 = 1 remainder 1
        *   1 / 2 = 0 remainder 1
        *   Read from bottom up: 11001
    *   **Fractional Part (0.375):** Convert to binary
        *   0.375 \* 2 = 0.75 (0)
        *   0.75 \* 2 = 1.5 (1)
        *   0.5 \* 2 = 1.0 (1)
        *   Read from top to bottom: 0.011
    *   Therefore, 25.375₁₀ = 11001.011₂
*   **g.** Using the Taylor series expansion of f(x) = cos(x) near x = 0, find an approximation of f(h) for small h
    *   Taylor Series Expansion formula: f(x) = f(a) + f'(a)(x-a) + f''(a)(x-a)²/2! + ...
    *   f(x) = cos(x) and a = 0
    *   f(0) = cos(0) = 1
    *   f'(x) = -sin(x)  => f'(0) = -sin(0) = 0
    *   f''(x) = -cos(x) => f''(0) = -cos(0) = -1
    *   f'''(x) = sin(x) => f'''(0) = sin(0) = 0
    *   f(x) = 1 + 0*(x-0) + (-1)(x-0)²/2! + 0*(x-0)³/3! + ...
    *   f(x) ≈ 1 - x²/2
    *   To find an approximation of f(h)
    *   f(h) ≈ 1 - h²/2
*   **h.** Given that f(2) = 6, f'(2) = -½ and f''(2) = 10, what is the most accurate Taylor polynomial approximation of f(2:2) that you can find?
    *   Here x = 2:2, which means x=2, a=2
    *   Taylor polynomial = f(a) + f'(a)(x-a) + f''(a)(x-a)²/2! + ...
    *   f(2) = 6
    *   f'(2) = -1/2
    *   f''(2) = 10
    *   Taylor polynomial ≈ 6 + (-1/2)(x-2) + (10(x-2)²)/2!
    *   Taylor polynomial ≈ 6 - 0.5(x-2) + 5(x-2)²
*   **i.** You are given a matrix u of size 4 x 1, u = \[2;1;1;1], and a second matrix v = \[0.5;1;0;0]. We now perform the matrix-matrix product w = u(vᵀ), where T denotes transpose.
    *   i. What is the size of matrix w?
    *   u is 4x1 and v is 4x1
    *   vᵀ is 1x4
    *   u * vᵀ  will result in a matrix of size 4x4
    *   ii. What is the value of w(1,1)?
    *   w = u \* vᵀ
    *   First column of w: \[2;1;1;1] \* 0.5 = \[1;0.5;0.5;0.5]
    *   w(1,1) = 1
*   **j.** Differentiate between order of an ODE and linearity of an ODE. Give examples
    *   **Order of an ODE:** The order is determined by the highest derivative present in the equation.
        *   Example: y'' + 2y' + y = 0  (Second-order ODE)
    *   **Linearity of an ODE:** An ODE is linear if:
        *   The dependent variable (and its derivatives) appear only to the first power.
        *   No products of the dependent variable and its derivatives.
        *   No non-linear functions of the dependent variable or its derivatives (e.g., sin(y), y²).
        *   Example (Linear): y'' + 2y' + y = 0
        *   Example (Non-linear): y'' + y² = 0

**Question 2**

*   **a.** Find the interval in which x³ - x - 4 = 0 lies.
    *   Let f(x) = x³ - x - 4
    *   To find an interval, you can use the Intermediate Value Theorem. You are looking for a change in sign of f(x)
    *   Try different values of x:
        *   f(0) = -4
        *   f(1) = -4
        *   f(2) = 8 - 2 - 4 = 2
        *   f(1.5) = 1.5³ - 1.5 - 4 = -2.125
        *   Therefore, a root exists between 1 and 2
*   **b.** Determine the roots correct to two decimal places using the bisection method.
    *   *f(x) = x³ - x - 4*
    *   *a = 1, b = 2*
    *   **Iteration 1:**
        *   c = (a + b) / 2 = (1 + 2) / 2 = 1.5
        *   f(1.5) = (1.5)³ - 1.5 - 4 = -2.125 < 0.  Since f(1.5) < 0 and f(2) > 0, the root lies between 1.5 and 2.
    *   **Iteration 2:**
        *   a = 1.5, b = 2
        *   c = (1.5 + 2) / 2 = 1.75
        *   f(1.75) = (1.75)³ - 1.75 - 4 = 0.140625 > 0. Since f(1.5) < 0 and f(1.75) > 0, the root lies between 1.5 and 1.75.
    *   **Iteration 3:**
        *   a = 1.5, b = 1.75
        *   c = (1.5 + 1.75) / 2 = 1.625
        *   f(1.625) = (1.625)³ - 1.625 - 4 = -0.908203 < 0. Since f(1.625) < 0 and f(1.75) > 0, the root lies between 1.625 and 1.75.
    *   **Iteration 4:**
        *   a = 1.625, b = 1.75
        *   c = (1.625 + 1.75) / 2 = 1.6875
        *   f(1.6875) = (1.6875)³ - 1.6875 - 4 = -0.36017 < 0.  Since f(1.6875) < 0 and f(1.75) > 0, the root lies between 1.6875 and 1.75.
    *   **Iteration 5:**
        *   a = 1.6875, b = 1.75
        *   c = (1.6875 + 1.75) / 2 = 1.71875
        *   f(1.71875) = (1.71875)³ - 1.71875 - 4 = -0.106888 < 0. Since f(1.71875) < 0 and f(1.75) > 0, the root lies between 1.71875 and 1.75.
    *   **Iteration 6:**
        *   a = 1.71875, b = 1.75
        *   c = (1.71875 + 1.75) / 2 = 1.734375
        *   f(1.734375) = (1.734375)³ - 1.734375 - 4 = 0.015248 > 0
        *   Since f(1.71875) < 0 and f(1.734375) > 0, the root lies between 1.71875 and 1.734375.
    *   **Iteration 7:**
        *   a = 1.71875, b = 1.734375
        *   c = (1.71875 + 1.734375) / 2 = 1.7265625
        *   f(1.7265625) = (1.7265625)³ - 1.7265625 - 4 = -0.046313
        *   Since f(1.7265625) < 0 and f(1.734375) > 0, the root lies between 1.7265625 and 1.734375.
    *   The root to two decimal places is 1.73

**Question 3**

*   **a.** State the Newton-Raphson method.
    *   The Newton-Raphson method is an iterative method for finding the roots (zeros) of a real-valued function.  It uses the tangent line at a current guess to find a better approximation of the root.
    *   Formula: `x_(n+1) = x_n - f(x_n) / f'(x_n)`
    *   Where:
        *   x_(n+1) is the next approximation of the root.
        *   x_n is the current approximation of the root.
        *   f(x_n) is the value of the function at x_n.
        *   f'(x_n) is the value of the derivative of the function at x_n.
*   **b.** What are the assumptions often made? Find the iterative methods based on the Newton-Raphson method for finding √N, where N is a positive real number. Apply the methods to N = 18 to obtain the results correct to two decimal places.
    *   **Assumptions for Newton-Raphson:**
        *   The function f(x) must be differentiable.  The derivative, f'(x), must exist.
        *   The initial guess, x₀, must be "close enough" to the actual root for the method to converge.
        *   The derivative, f'(x), should not be zero (or close to zero) near the root, as this would cause division by zero.
    *   **Finding √N using Newton-Raphson:**
        *   We want to find the root of the equation x² - N = 0
        *   f(x) = x² - N
        *   f'(x) = 2x
        *   Newton-Raphson formula: x_(n+1) = x_n - (x_n² - N) / (2x_n)
        *   Simplifying: x_(n+1) = (x_n + N/x_n) / 2
    *   **Applying to N = 18:**
        *   x_(n+1) = (x_n + 18/x_n) / 2
        *   Start with an initial guess, x₀.  Let's start with x₀ = 4.
        *   **Iteration 1:**
            *   x₁ = (4 + 18/4) / 2 = 4.25
        *   **Iteration 2:**
            *   x₂ = (4.25 + 18/4.25) / 2 ≈ 4.242647
        *   **Iteration 3:**
            *   x₃ = (4.242647 + 18/4.242647) / 2 ≈ 4.242641
        *   Iteration 4:
            *   x₄ = (4.242641 + 18/4.242641) / 2 ≈ 4.242641
        *   √18 ≈ 4.24 (to two decimal places)

**Question 4**

*   **a.** Highlight any three (3) methods of solutions to ODE problems
    *   Euler's Method (covered in the previous example)
    *   Runge-Kutta Methods (various orders, more accurate than Euler's)
    *   Taylor Series Method
    *   Finite Difference Methods
    *   Finite Element Methods
    *   Variation of Parameters
*   **b.** Use Euler method to solve the ODE: f(x,y) = 1 + x², x₀ = 1, y₀ = -4, h=0.01.
    *   From Euler's method,  `y_(i+1) = y_i + h \* f(x_i, y_i)`
    *   We want to find y(x) given x = 1 and 1 step to x=1.01 with a step size of 0.01
    *   x₀ = 1, y₀ = -4, h = 0.01
    *   f(x, y) = 1 + x²
    *   **Iteration 1:**
        *   y₁ = y₀ + h \* f(x₀, y₀)
        *   y₁ = -4 + 0.01 \* (1 + 1²)
        *   y₁ = -4 + 0.01 \* 2
        *   y₁ = -3.98

**Question 5**

*   **a.** Find the roots of f(x) = x⁵ + x³ + 3, with initial points x₀ = -1 and x₁ = -1.1 using secant method with error < 0.001
    *   **Secant Method Formula:**  x_(n+1) = x_n - f(x_n) \* (x_n - x_(n-1)) / (f(x_n) - f(x_(n-1)))
    *   f(x) = x⁵ + x³ + 3
    *   f'(x) = 5x⁴ + 3x²
    *   x₀ = -1, x₁ = -1.1
    *   **Iteration 1:**
        *   f(x₀) = f(-1) = (-1)⁵ + (-1)³ + 3 = 1
        *   f(x₁) = f(-1.1) = (-1.1)⁵ + (-1.1)³ + 3 = -0.061
        *   x₂ = x₁ - f(x₁) \* (x₁ - x₀) / (f(x₁) - f(x₀))
        *   x₂ = -1.1 - (-0.061) * (-1.1 - (-1)) / (-0.061 - 1)
        *   x₂ = -1.1 + 0.061 * 0.1 / 1.061 = -1.1 - .00057
        *   x₂ = -1.09943 (Error = |-1.1 - (-1.09943)| = .00057
    *   **Iteration 2:**
        *   f(x₂) = f(-1.09943) =  (-1.09943)⁵ + (-1.09943)³ + 3 = -0.00000002871
        *   x₃ = x₂ - f(x₂) \* (x₂ - x₁) / (f(x₂) - f(x₁))
        *   x₃ = -1.09943 - (0) * (-1.09943 - (-1.1)) / (0 - (-0.061)) = -1.09943
        *   Error is very small, we can assume this answer is correct

*   **b.** What differentiate secant method from Newton's method?
    *   **Secant Method:**
        *   Approximates the derivative, f'(x), using a difference quotient. (uses the slope of a secant line).
        *   Requires *two* initial guesses, x₀ and x₁.
        *   Generally slower convergence rate than Newton's method, but faster than Bisection.
        *   Does not require the evaluation of the derivative.
    *   **Newton's Method:**
        *   Uses the derivative, f'(x), directly. (uses the tangent line)
        *   Requires *one* initial guess, x₀.
        *   Generally faster convergence (when it converges) than the secant method (quadratic convergence).
        *   Requires the evaluation of the derivative at each iteration.

**Question 6**

*   **Use Cramer's rule to solve**
    *   x₁ + x₂ = 3; x₁ + 2x₂ = 5
    *   **Cramer's Rule** is a method for solving systems of linear equations using determinants.
    *   Write the system of equations in matrix form, i.e.
        *   \[1 1; 1 2] \[x1;x2] = \[3;5]
    *   Find the determinant of the coefficient matrix (A):
        *   det(A) = (1 \* 2) - (1 \* 1) = 1
    *   Replace the first column of the coefficient matrix (A) with the constant vector to find A1
        *   \[3 1; 5 2]
        *   det(A1) = (3 \* 2) - (1 \* 5) = 1
    *   Replace the second column of the coefficient matrix (A) with the constant vector to find A2
        *   \[1 3; 1 5]
        *   det(A2) = (1 \* 5) - (3 \* 1) = 2
    *   Calculate the values of the variables:
        *   x1 = det(A1)/det(A) = 1/1 = 1
        *   x2 = det(A2)/det(A) = 2/1 = 2
    *   Solution: x₁ = 1, x₂ = 2

*   **Find a function of the form ae^(bx) that best fits the data below:**

| x | 1   | 2   | 3   |
|---|- ---|- ---|- ---|
| y | 2.4 | 5   | 9   |

    *   To solve this problem we can linearize the function: y = ae^(bx)
    *   Take the natural log of each side, ln(y) = ln(a) + bx
    *   Let z = ln(y), A = ln(a)
    *   Now the function can be represented as z = A + bx.
    *   Make a table

| x | 1    | 2    | 3     |
|---|- ----|- ----|- -----|
| y | 2.4  | 5    | 9     |
| z | .875 | 1.61 | 2.197 |

    *   There are 3 points, so we can solve for A and B.

        *   0.875 = A + B
        *   1.61 = A + 2B
        *   2.197 = A + 3B
    *   1.61 - 0.875 = B
    *   B = 0.735
    *   0.875 = A + 0.735
    *   A = 0.14
    *   Therefore,
        *   b = 0.735
        *   ln(a) = 0.14
        *   a = e^0.14 = 1.15
        *   **y ≈ 1.15 * e^(0.735x)**
