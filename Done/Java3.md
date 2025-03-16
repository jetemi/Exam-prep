**SECTION A**

**Q1a. Define: (i) An Object (ii) A class**

**(i) An Object:**

An **object** is an **instance** of a class.  Objects have:

*   **State (Attributes/Properties):** Data that describes the object. These are represented by variables. For example, a `Car` object might have state like `color`, `model`, `speed`.
*   **Behavior (Methods):** Actions that an object can perform. These are represented by methods. For example, a `Car` object might have behaviors like `accelerate()`, `brake()`, `turn()`.

**(ii) A class:**

A **class** is a blueprint or a template for creating objects. It defines the type of objects that will be created from it.  It specifies:

*   **Attributes (Data Members/Fields):** The types of data objects of this class will hold.
*   **Methods (Member Functions/Behaviors):** The actions objects of this class can perform.

Think of a class as a cookie cutter, and objects as the cookies made using that cutter. The class defines the shape and properties of the cookies, while each cookie is an individual object.

**Q1b. i. Write a program that create a constructor for class puppy which prints ("Puppy is a white dog we call it" + name), create an object myPuppy to call the constructor created, pass the variable Tommy to the name in the constructor.**

```java
class Puppy {
    String name; // Instance variable to store the puppy's name

    // Constructor for the Puppy class
    public Puppy(String puppyName) {
        name = puppyName;
        System.out.println("Puppy is a white dog we call it " + name);
    }

    public static void main(String[] args) {
        String puppyName = "Tommy";
        Puppy myPuppy = new Puppy(puppyName); // Creating an object and calling the constructor
    }
}
```

**ii. Display the output. (2 Mrks)**

**Output:**

```
Puppy is a white dog we call it Tommy
```

**Q2a. State the syntax for creating a method and explain each part.**

*(This is a repeated question, but let's provide the syntax and explanation again for clarity.)*

The general syntax for creating a method in Java is:

```java
[access_modifier] [return_type] method_name([parameter_list]) {
    // Method body - code to be executed
    [return value;] // Optional, if return_type is not void
}
```

**Explanation of each part:**

*   **`[access_modifier]` (Optional):**  Specifies the visibility or accessibility of the method. Common access modifiers are:
    *   `public`: Method is accessible from anywhere.
    *   `private`: Method is accessible only within the same class.
    *   `protected`: Method is accessible within the same package and by subclasses in other packages.
    *   `default` (no modifier): Method is accessible only within the same package.

*   **`[return_type]`:**  Specifies the data type of the value that the method will return after execution.
    *   It can be any primitive data type (e.g., `int`, `double`, `boolean`), a reference type (e.g., `String`, `Array`, class name), or `void` if the method does not return any value.

*   **`method_name`:**  The identifier (name) of the method. Method names should follow Java naming conventions (typically start with a lowercase letter and use camelCase for multiple words).

*   **`([parameter_list])` (Optional):**  A comma-separated list of parameters enclosed in parentheses. Parameters are input values that the method can receive and use. Each parameter consists of:
    *   `data_type`: The data type of the parameter.
    *   `parameter_name`: The identifier (name) of the parameter.
    *   If the method has no parameters, the parentheses are empty `()`.

*   **`{ ... }` (Method body):**  The block of code enclosed in curly braces `{}` that contains the statements to be executed when the method is called. This is where the actual logic and operations of the method are implemented.

*   **`[return value;]` (Optional):**  If the `return_type` is not `void`, the method must include a `return` statement to send a value back to the caller. The `return` value must be of the data type specified in the `return_type`. If `return_type` is `void`, no `return` statement with a value is needed (though you can use `return;` to exit the method early).

**Q2b. Write a program to declare a method and call it as stated below:**

**(i) Declare and define a method to find the maximum of two integer numbers.**

```java
class MethodExample {
    // Method to find the maximum of two integers
    public static int findMaximum(int num1, int num2) {
        if (num1 > num2) {
            return num1;
        } else {
            return num2;
        }
    }

    public static void main(String[] args) {
        // ... (rest of the main method will be in part (ii))
    }
}
```

**(ii) Call and print the output of the method in the main class.**

```java
class MethodExample {
    // Method to find the maximum of two integers
    public static int findMaximum(int num1, int num2) {
        if (num1 > num2) {
            return num1;
        } else {
            return num2;
        }
    }

    public static void main(String[] args) {
        int number1 = 15;
        int number2 = 8;

        int maximum = findMaximum(number1, number2); // Calling the findMaximum method

        System.out.println("The maximum of " + number1 + " and " + number2 + " is: " + maximum);
    }
}
```

**(iii) Display the output of the program.**

**Output:**

```
The maximum of 15 and 8 is: 15
```

**Q3a. What happens in a while- loop if the control condition is false (i.e., zero) initially?**

If the control condition of a `while` loop is **false** (or evaluates to zero in languages where 0 is treated as false, although in Java boolean conditions are used), **initially**, the loop body will **not execute even once**.

**Explanation:**

The `while` loop works by first evaluating the condition. If the condition is true, the loop body is executed. After the loop body executes, the condition is checked again. This process repeats as long as the condition remains true.

However, if the condition is false from the very beginning (before the loop even starts its first iteration), the condition check fails immediately.  As a result, the program execution will skip over the entire loop body and proceed to the statement immediately following the `while` loop.

**Example:**

```java
int count = 0;
while (count > 0) { // Condition is initially false (0 is not greater than 0)
    System.out.println("This will not be printed.");
    count--;
}
System.out.println("Loop finished."); // This will be printed.
```

**Output:**

```
Loop finished.
```

In this example, because `count` is initialized to 0, the condition `count > 0` is false from the start. Therefore, the `System.out.println("This will not be printed.");` line inside the loop is never executed. Only "Loop finished." is printed.

**Q3b. When should the control variable in a for- loop be declared before the loop (instead of within its control mechanism)?**

Generally, it's recommended to declare the control variable **within the initialization part of the `for` loop**.

1.  **When you need to access the control variable's value *after* the loop finishes:** If you need to use the final value of the control variable after the loop has completed, you must declare it outside the loop's scope.

    ```java
    int i; // Declared outside the loop
    for (i = 0; i < 10; i++) {
        // Loop body
    }
    System.out.println("Value of i after loop: " + i); // Accessing 'i' after the loop
    ```

2.  **When the initial value or scope of the control variable is determined outside the loop:** If the starting value of the control variable is determined based on some condition or input before the loop begins, you might initialize it before the loop.

    ```java
    int startValue = 5; // Initial value determined elsewhere
    for (int i = startValue; i < 15; i++) { // Using pre-determined startValue
        // Loop body
    }
    ```

3.  **In certain less common scenarios related to loop control flow:** In rare cases, you might have a more complex loop control structure where the initialization or update of the control variable is managed outside the standard `for` loop increment/decrement part. While less common in simple counter-controlled loops, it can occur in more advanced scenarios.

**In summary:**  Declare the loop control variable *within* the `for` loop header for most standard counter-controlled loops to limit scope and improve readability. Declare it *outside* only when you explicitly need to access the variable's value after the loop or when its initialization is determined externally.

**Q3c. How does the break statement provide better control of loops?**

The `break` statement provides **finer-grained control** over loop execution by allowing you to **terminate the loop prematurely** based on a specific condition encountered *within* the loop body.  This enhances control in several ways:

1.  **Early Exit Based on Condition:**  `break` allows you to exit a loop before it would naturally terminate based on its loop-continuation condition. This is useful when you've found what you're looking for or encountered a situation where further iterations are unnecessary or undesirable.

    *   **Example: Searching for an element in an array:** Once you find the target element, you can use `break` to stop searching and exit the loop, improving efficiency.

2.  **Handling Special Cases:** `break` can be used to handle exceptional or special cases within a loop. If a particular condition arises that requires immediate loop termination, `break` provides a way to handle it directly.

    *   **Example: Input validation loop:** If the user enters invalid input within a loop that's supposed to continue until valid input is received, you might use `break` to exit the loop if a certain number of invalid attempts are made.

3.  **Simplifying Complex Loop Conditions:** In some situations, using a `break` statement can make the loop's main condition simpler and more readable. Instead of creating a very complex loop-continuation condition to cover all exit scenarios, you can use a simpler condition and handle specific exit cases with `break` within the loop body.

    *   **Example:** A loop that needs to terminate based on multiple different conditions. You can use a `while(true)` loop with `break` statements inside to exit based on each condition, potentially making the logic clearer than a single complex `while` condition.

**Without `break`:** Without `break`, you would have to rely solely on the loop-continuation condition to control loop termination. This can sometimes lead to:

*   More complex and harder-to-read loop conditions.
*   Less efficient code (if you have to continue iterating even after the desired condition is met).
*   Less flexible handling of special cases within loops.

**In essence, `break` provides a mechanism for "programmatic loop exit" from within the loop body, adding flexibility and control beyond just the loop-continuation condition.**

**Q3d. Write a program to compute the sum of odd numbers between 1 and 100.**

*(This is a repeated question, but let's provide the Java code again for completeness.)*

```java
public class SumOfOddNumbers {
    public static void main(String[] args) {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            if (i % 2 != 0) { // Check if i is odd (remainder when divided by 2 is not 0)
                sum += i;
            }
        }
        System.out.println("The sum of odd numbers between 1 and 100 is: " + sum);
    }
}
```

**SECTION B**

**1. Which of the following is true? (a) Comments cause the computer to print the text after the // on the screen when the program executes (b) All variables must be given a type when they're declared (c) Java considers the variables number and Number to be identical (d) The remainder operator (%) can be used only with integer operands**

**Correct Answer:** (b) All variables must be given a type when they're declared

**2. A syntax error is also called (a) compiler error (b) compile-time error (c) compilation error (d) All of the above**

**Correct Answer:** (d) All of the above

**3. Which of the following is false? (a) Java class name (a)is an identifier consisting of letters, digits, underscores (\_) and dollar signs ($) that does not begin with a digit (b) contains spaces (c) a and b**

**Correct Answer:** (b) contains spaces

**4. The body of every class declaration is delimited by braces (a) True (b) False**

**Correct Answer:** (a) True

**5. An end-of-line comment (a) /\* \*/ (b) /\*/ (c) // (d) All of the above**

**Correct Answer:** (c) //

**Explanation:**

**6. The body of every method begins with (a) { (b) } (c) ( (d) )**

**Correct Answer:** (a) {

**7. Which of the following operators has the lowest precedence? (a) \* (b) / (c) + (d) %**

**Correct Answer:** (c) +

**8. x = 2 % 2 + 2 \* 2 / 2 gives (a) 1 (b) 2 (c) 3 (d) 4**

**Correct Answer:** (b) 2

**9. x = (3 \* 9 \* (3 + (9 \* 3 / 3)))) gives (a) 1 (b) 127 (b) 324 (d) 81 (d) 243**

**Correct Answer:** (b) 324

**10. if c=5, printf(c++) will give the value (a) 5 (b) 6 (c) 7 (d) 25**

**Correct Answer:** (a) 5

**11. if c=5, printf(++c) will give the value (a) 5 (b) 6 (c) 7 (d) 25**

**Correct Answer:** (b) 6

**12. What is the trip count of the loop defined as for (int counter = 1; counter < 10; counter+=+) ? (a) 11 (b) 10 (c) 9 (d) 1**

**Correct Answer:** (c) 9

**Explanation:**

**13. The precedence of <= is higher than that of ++ (a) True (b) False**

**Correct Answer:** (b) False

**14. Java programs normally go through the following phases except (a) edit (b) evaluate (c) compile (d) load**

**Correct Answer:** (b) evaluate

**15. Objects allow the design practice of information hiding (a) True (b) False**

**Correct Answer:** (a) True

**16. Size, shape, color, and weight of an object are considered -------- of the objects class (a) description (b) attributes (c) methods (d) identifiers**

**Correct Answer:** (b) attributes

**17. Which of the following is true? (a) Comments cause the computer to print the text after the // on the screen when the program executes (b) All variables must be given a type when they're declared (c) Java considers the variables number and NumBer to be identical (d) Java considers the variables number and NumBer to be identical**

**Correct Answer:** (b) All variables must be given a type when they're declared

**18. if (c < 7), System.out.println("c is less than 7"); contains an error (a) True (b) False**

**Correct Answer:** (b) False

**19. Which of the following is false? (a) By convention, method names begin with an uppercase first letter, and all subsequent words in the name begin with a capital first letter (b) An import declaration is not required when one class in a package uses another in the same package (c) Empty parentheses following a method name in a method declaration indicate that the method does not require any parameters to perform its task (d) Any class that contains public static void main(String[] args) can be used to execute an app**

**Correct Answer:** (a) By convention, method names begin with an uppercase first letter, and all subsequent words in the name begin with a capital first letter

**20. The statement for accepting input from the user in java is (a) cin (b) input.nextInt() (c) input int (d) All of the above**

**Correct Answer:** (b) input.nextInt()