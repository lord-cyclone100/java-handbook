#### [Go Back ↩](../README.md)

## Java Handbook

### Variables in Java

Variables are used to store data values in Java. Every variable in Java has a data type that defines the kind of values it can hold. Java is a statically typed language, meaning that variable types must be explicitly declared before usage.

#### Example Program:
```java
public class VariableExample {
    public static void main(String[] args) {
        int age = 25;  // Integer variable
        double price = 10.5;  // Floating point variable
        char grade = 'A';  // Character variable
        String name = "John";  // String variable
        
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Grade: " + grade);
        System.out.println("Price: " + price);
    }
}
```

#### Explanation of Terms:
- **int**: A data type used to store whole numbers.
- **double**: A data type for floating-point numbers with decimal values.
- **char**: Used for storing a single character.
- **String**: A class representing a sequence of characters.
- **System.out.println()**: Prints the output to the console.

---

### Control Flow Statements in Java

Control flow statements determine the execution flow of a Java program. Common statements include if-else, loops (for, while), and switch-case.

#### Example Program:
```java
public class ControlFlowExample {
    public static void main(String[] args) {
        int num = 10;
        
        // If-else statement
        if (num > 0) {
            System.out.println("Positive Number");
        } else {
            System.out.println("Negative Number");
        }

        // For loop
        for (int i = 1; i <= 5; i++) {
            System.out.println("Iteration: " + i);
        }
    }
}
```

#### Explanation:
- **if-else**: Executes a block of code based on a condition.
- **for loop**: Repeats a block of code a specific number of times.

---

### Methods in Java

Methods in Java allow code reuse by encapsulating a block of statements. Methods can have parameters and return values.

#### Example Program:
```java
public class MethodExample {
    public static void main(String[] args) {
        int sum = addNumbers(5, 10);
        System.out.println("Sum: " + sum);
    }
    
    public static int addNumbers(int a, int b) {
        return a + b;
    }
}
```

#### Explanation:
- **Methods**: Reusable blocks of code that perform a specific task.
- **Parameters**: Values passed to methods to perform operations.
- **return**: Used to return a value from a method.



