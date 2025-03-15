**1a. Briefly describe each object-oriented programming concept:**

**(i) Class:**
A class is a blueprint or template for creating objects. It defines the data (attributes or properties) that objects of the class will hold and the actions (methods or behaviors) that objects of the class can perform. Think of it like a cookie cutter – the class is the cutter, and the objects are the cookies.

**(ii) Objects:**
An object is an instance of a class. It's a real-world entity that has state (data) and behavior (methods).  When you create an object from a class, you are essentially bringing the blueprint to life. For example, if "Car" is a class, then "MyRedCar" is an object of the class "Car."

**(iii) Data Abstraction:**
Data abstraction is the process of hiding complex implementation details and showing only the essential information to the user. It focuses on *what* an object does rather than *how* it does it.  For instance, when you use a TV remote, you interact with buttons (abstraction) without needing to know the intricate electronics inside. In programming, this is achieved through abstract classes and interfaces.

**(iv) Encapsulation:**
Encapsulation is the bundling of data (attributes) and methods that operate on that data within a single unit called a class. It helps in protecting data from unauthorized access and modification.  This is often implemented using access modifiers like `private`, `protected`, and `public` to control visibility.  Imagine a capsule containing medicine; encapsulation keeps the data and methods together and protected.

**(v) Inheritance:**
Inheritance is a mechanism that allows a new class (child class or subclass) to inherit properties and methods from an existing class (parent class or superclass). It promotes code reusability and establishes an "is-a" relationship between classes.  For example, a "SportsCar" class can inherit from a "Car" class, inheriting common car properties but adding specific sports car features.

**(vi) Polymorphism:**
Polymorphism means "many forms." In OOP, it refers to the ability of an object to take on many forms.  This can be achieved through:
    * **Method Overloading (Compile-time polymorphism):**  Having multiple methods with the same name but different parameters within the same class. The correct method is chosen based on the arguments passed at compile time.
    * **Method Overriding (Runtime polymorphism):**  A subclass providing a specific implementation for a method that is already defined in its superclass. The correct method to be executed is determined at runtime based on the object's actual type.

**(vii) Dynamic Binding:**
Dynamic binding (or late binding) is the process of linking a method call to the actual method implementation at runtime.  This is crucial for polymorphism, especially method overriding. When you call a method on an object, the system determines which method to execute based on the object's type at runtime, not at compile time. This allows for flexibility and adaptability in program behavior.

**(viii) Message Passing:**
Message passing is the way objects communicate with each other in OOP.  Objects interact by sending messages to each other, requesting services or information.  A message typically consists of:
    * The object to which the message is sent (receiver).
    * The name of the method to be invoked (message).
    * Any arguments or data to be passed along with the message.
  When an object receives a message, it invokes the corresponding method to handle the request.

**1b. Differentiate between run time error and compile time error:**

| Feature         | Compile Time Error                                  | Run Time Error                                      |
|-----------------|----------------------------------------------------|------------------------------------------------------|
| **Detection**   | Detected by the compiler during compilation.       | Detected during program execution.                    |
| **Cause**       | Syntax errors, type errors, undeclared variables, etc. | Logic errors, invalid input, resource unavailability, etc. |
| **Prevention**  | Can be prevented by writing syntactically correct code and adhering to language rules. | Can be prevented by careful program design, input validation, and error handling (e.g., try-catch blocks). |
| **Example**     | `int x = "hello";` (Type mismatch)              | `int result = 10 / 0;` (Division by zero)          |
| **Impact**      | Program compilation fails; executable not created. | Program compilation succeeds, but program crashes or behaves unexpectedly during execution. |

**1c. Why do we need object-oriented programming?**

* **Modularity:** OOP promotes breaking down complex problems into smaller, manageable objects. This makes code easier to understand, develop, and debug.
* **Reusability:** Inheritance allows you to reuse code from existing classes, reducing development time and effort. You can build upon existing functionalities instead of starting from scratch.
* **Maintainability:** OOP principles like encapsulation and abstraction make code more organized and less prone to errors. Changes in one part of the code are less likely to affect other parts, making maintenance easier.
* **Real-world Modeling:** OOP allows you to model real-world entities and their interactions more naturally using objects and classes. This makes it easier to design and understand complex systems.
* **Problem Solving:** OOP provides a structured approach to problem-solving by focusing on objects and their relationships. This can simplify the design process for large and complex software projects.
* **Abstraction and Complexity Management:** Abstraction helps manage complexity by hiding unnecessary details and presenting a simplified view of objects.
* **Teamwork and Collaboration:** OOP principles facilitate better teamwork as objects can be developed and maintained independently, allowing for parallel development.

**2a. A class of ten students took a quiz... Write a pseudocode to determine the class average on the quiz.**

```pseudocode
BEGIN
  // Initialize variables
  DECLARE total_grades AS INTEGER
  DECLARE average_grade AS REAL
  DECLARE grade AS INTEGER
  DECLARE student_count AS INTEGER

  SET total_grades = 0
  SET student_count = 10

  // Loop through each student to get their grade
  FOR i FROM 1 TO student_count DO
    DISPLAY "Enter grade for student " + i + ": "
    INPUT grade

    // Validate grade (optional, but good practice)
    IF grade < 0 OR grade > 100 THEN
      DISPLAY "Invalid grade. Please enter a grade between 0 and 100."
      // You might want to handle invalid input more robustly (e.g., re-prompt)
    ELSE
      ADD grade TO total_grades
    ENDIF
  ENDFOR

  // Calculate the average
  average_grade = total_grades / student_count

  // Display the class average
  DISPLAY "The class average is: " + average_grade
END
```

**2b. Write a JAVA program for (2a) above.**

```java
import java.util.Scanner;

public class ClassAverage {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int totalGrades = 0;
        int studentCount = 10;

        System.out.println("Enter grades for " + studentCount + " students (0-100):");

        for (int i = 1; i <= studentCount; i++) {
            System.out.print("Enter grade for student " + i + ": ");
            int grade = input.nextInt();

            if (grade < 0 || grade > 100) {
                System.out.println("Invalid grade. Please enter a grade between 0 and 100.");
                i--; // Decrement i to re-enter grade for the current student
            } else {
                totalGrades += grade;
            }
        }

        double averageGrade = (double) totalGrades / studentCount;
        System.out.println("The class average is: " + averageGrade);

        input.close();
    }
}
```

**3a. Write JAVA statements to accomplish each of the following tasks:**

**(i) Use one statement to assign the sum of x and y to z, then increment x by 1.**

```java
z = x + y; x++;
```

**(ii) Test whether variable count is greater than 10. If it is, print "Count is greater than 10".**

```java
if (count > 10) {
    System.out.println("Count is greater than 10");
}
```

**(iii) Use one statement to decrement the variable x by 1, then subtract it from variable total and store the result in variable total.**

```java
total -= --x;
```

**(iv) Calculate the remainder after q is divided by divisor, and assign the result to q.**

```java
q = q % divisor;
```

**3b. Write a JAVA program to compute n factorial.**

```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a non-negative integer n to compute factorial: ");
        int n = input.nextInt();

        if (n < 0) {
            System.out.println("Factorial is not defined for negative numbers.");
        } else {
            long factorial = 1;
            for (int i = 1; i <= n; i++) {
                factorial *= i;
            }
            System.out.println("Factorial of " + n + " is: " + factorial);
        }
        input.close();
    }
}
```

**4a. Differentiate break and continue statements.**

| Feature         | `break` Statement                               | `continue` Statement                               |
|-----------------|----------------------------------------------------|-------------------------------------------------------|
| **Purpose**     | Terminates the loop execution immediately.       | Skips the rest of the current iteration and proceeds to the next iteration. |
| **Loop Exit**   | Exits the loop entirely.                           | Does not exit the loop; only the current iteration.   |
| **Control Flow**| Transfers control to the statement immediately following the loop. | Transfers control to the loop's update statement (for `for` loop) or condition check (for `while` and `do-while` loops). |
| **Usage**       | Used to exit a loop prematurely based on a condition (e.g., finding a specific element). | Used to skip certain iterations based on a condition without exiting the loop entirely (e.g., skipping processing of certain elements). |

**4b(i). Describe the four basic elements of counter-controlled repetition.**

Counter-controlled repetition, typically implemented using `for` loops, involves these four basic elements:

1.  **Initialization:**  A control variable is initialized to a starting value. This is usually done before the loop begins or as part of the `for` loop header.  e.g., `int count = 0;` or `for (int count = 0; ...)`
2.  **Condition (Loop-continuation condition):** A condition is evaluated before each iteration to determine if the loop should continue executing. The loop continues as long as the condition is true. e.g., `count < 10` or `i <= n`
3.  **Increment/Decrement (Update):** The control variable is incremented or decremented in each iteration. This step ensures that the loop eventually terminates by making the loop-continuation condition false. e.g., `count++;` or `i--`
4.  **Loop Body:** The statements that are to be repeated within the loop. These statements are executed in each iteration as long as the loop-continuation condition is true.

**4b(ii). Compare and contrast the while and for repetition statements.**

| Feature         | `while` loop                                      | `for` loop                                         |
|-----------------|---------------------------------------------------|------------------------------------------------------|
| **Structure**   | `while (condition) { // loop body }`           | `for (initialization; condition; increment/decrement) { // loop body }` |
| **Control Variable** | Initialization and increment/decrement are handled separately, typically before and within the loop body. | Initialization, condition, and increment/decrement are all defined in the loop header, making it more compact for counter-controlled loops. |
| **Readability (Counter-Controlled)** | Less readable for counter-controlled loops as control variable management is scattered. | More readable for counter-controlled loops as all control elements are in one place (header). |
| **Use Cases**   | Best suited when the number of iterations is not known in advance and depends on a condition. (Condition-controlled loops) | Best suited for counter-controlled loops where the number of iterations is known or can be determined easily, and you have initialization, condition, and update steps. |
| **Flexibility** | More flexible for complex loop conditions and updates that might not fit the standard increment/decrement pattern. | Less flexible for very complex conditions or updates compared to `while` loop, but sufficient for most counter-controlled scenarios. |

**4b(iii). Discuss a situation in which it would be more appropriate to use a do...while statement than a while statement. Explain why.**

* **`while` loop:** The condition is checked *before* the loop body is executed. If the condition is initially false, the loop body will not execute even once.
* **`do...while` loop:** The loop body is executed *first*, and then the condition is checked *after*. This ensures that the loop body runs at least one time, even if the condition is false from the beginning.

```java
import java.util.Scanner;

public class DoWhileExample {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int number;

        do {
            System.out.print("Enter a number between 1 and 10: ");
            number = input.nextInt();
        } while (number < 1 || number > 10); // Condition checked AFTER first execution

        System.out.println("You entered a valid number: " + number);
        input.close();
    }
}
```

In this example, even if the user initially enters an invalid number (e.g., 0 or 15), the `do...while` loop will execute the prompt and input part at least once. The `while` condition then checks if the entered number is within the valid range.

**4c. A person invests $1,000 in a savings account... Write a JAVA program to calculate and print the amount of money in the account at the end of each year for 10 years.**

```java
public class SavingsAccount {
    public static void main(String[] args) {
        double principal = 1000.0; // Initial deposit
        double interestRate = 0.05; // 5% annual interest rate
        int years = 10;

        System.out.println("Year\tAmount on deposit");
        System.out.println("----\t------------------");

        for (int year = 1; year <= years; year++) {
            principal = principal * (1 + interestRate); // Formula: a = p(1 + r)^n
            System.out.println(year + "\t$" + String.format("%.2f", principal)); // Format to 2 decimal places
        }
    }
}
```

**5a. Differentiate between branching and looping.**

| Feature         | Branching                                       | Looping                                         |
|-----------------|---------------------------------------------------|------------------------------------------------------|
| **Purpose**     | Control the flow of execution based on conditions. | Repeat a block of code multiple times.              |
| **Execution**   | Executes one block of code among several options. | Executes the same block of code repeatedly.         |
| **Control Flow**| Selects a path of execution based on a condition. | Repeats execution until a condition is met or a counter reaches a limit. |
| **Statements**  | `if`, `else if`, `else`, `switch`                 | `for`, `while`, `do-while`                           |
| **Example**     | Checking if a number is positive, negative, or zero. | Printing numbers from 1 to 100.                     |

**5b. Write a JAVA program to compute the sum of odd numbers between 1 and 100.**

```java
public class SumOfOddNumbers {
    public static void main(String[] args) {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            if (i % 2 != 0) { // Check if i is odd
                sum += i;
            }
        }
        System.out.println("The sum of odd numbers between 1 and 100 is: " + sum);
    }
}
```

**5c. Find and correct the error(s) in each of the following segments of code:**

**(i) For (i = 100, i >= 1, i++)**

**Error:** Incorrect syntax in the `for` loop initialization and increment/decrement part. Semicolons should separate the initialization, condition, and increment/decrement parts.  Also, `i++` is incrementing, but the loop is intended to go from 100 down to 1, so it should be decrementing.

**Corrected Code:**

```java
for (int i = 100; i >= 1; i--) { // Corrected syntax and decrement
    System.out.println(i);
}
```

**(ii) The following code should output the odd integers from 19 to 1:**
**for (i = 19; i >= 1; i += 2)**

**Error:**  The increment `i += 2` is incorrect for decrementing from 19 down to 1.  To get odd numbers in descending order, you need to *decrement* by 2.

**Corrected Code:**

```java
for (int i = 19; i >= 1; i -= 2) { // Corrected increment to decrement by 2
    System.out.println(i);
}
```

**6a. Write a JAVA program to compute the roots of a quadratic equation.**

```java
import java.util.Scanner;
import java.lang.Math; // Import Math class for sqrt and pow

public class QuadraticEquation {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("Enter coefficients a, b, and c for the quadratic equation ax^2 + bx + c = 0:");
        System.out.print("a = ");
        double a = input.nextDouble();
        System.out.print("b = ");
        double b = input.nextDouble();
        System.out.print("c = ");
        double c = input.nextDouble();

        double discriminant = b * b - 4 * a * c;

        if (discriminant > 0) {
            double root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
            double root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
            System.out.println("Roots are real and distinct:");
            System.out.println("Root 1 = " + root1);
            System.out.println("Root 2 = " + root2);
        } else if (discriminant == 0) {
            double root = -b / (2 * a);
            System.out.println("Roots are real and equal:");
            System.out.println("Root = " + root);
        } else { // discriminant < 0
            double realPart = -b / (2 * a);
            double imaginaryPart = Math.sqrt(Math.abs(discriminant)) / (2 * a);
            System.out.println("Roots are complex and imaginary:");
            System.out.println("Root 1 = " + realPart + " + " + imaginaryPart + "i");
            System.out.println("Root 2 = " + realPart + " - " + imaginaryPart + "i");
        }
        input.close();
    }
}
```

**6b. Draw a flowchart for (6a) above.**

```mermaid
graph TD
    A[Start] --> B{Input a, b, c};
    B --> C{Calculate Discriminant (D = b*b - 4*a*c)};
    C --> D{Is D > 0?};
    D -- Yes --> E[Calculate Root 1 = (-b + sqrt(D)) / (2*a)];
    E --> F[Calculate Root 2 = (-b - sqrt(D)) / (2*a)];
    F --> G[Display "Roots are real and distinct", Root 1, Root 2];
    D -- No --> H{Is D == 0?};
    H -- Yes --> I[Calculate Root = -b / (2*a)];
    I --> J[Display "Roots are real and equal", Root];
    H -- No --> K[Calculate Real Part = -b / (2*a)];
    K --> L[Calculate Imaginary Part = sqrt(abs(D)) / (2*a)];
    L --> M[Display "Roots are complex and imaginary", Real Part + " + " + Imaginary Part + "i", Real Part + " - " + Imaginary Part + "i"];
    G --> N[End];
    J --> N;
    M --> N;
```