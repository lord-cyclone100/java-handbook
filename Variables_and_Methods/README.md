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

#### Example Programs:

- If - else and For loop statement
```java
public class ControlFlowExample {
    public static void main(String[] args) {
        int num = 10;
        
        // If-else statement
        if (num > 0) {
            System.out.println("Positive Number");
        } else if (num < 0) {
            System.out.println("Negative Number");
        } else {
            System.out.println("Number is 0");
        }

        // Note : Both 'else if' block and 'else' block are optional.


        // For loop
        for (int i = 1; i <= 5; i++) {
            System.out.println("Iteration: " + i);
        }
    }
}
```

```java
public class ControlFlowExample {
  public static void main(String[] args) {
    int i = 0;
    while (i < 5) {
      System.out.println(i);
      i++;
    }  
  }
}
```

```java
public class ControlFlowExample {
  public static void main(String[] args) {
    int day = 4;
    switch (day) {
      case 1:
        System.out.println("Monday");
        break;
      case 2:
        System.out.println("Tuesday");
        break;
      case 3:
        System.out.println("Wednesday");
        break;
      case 4:
        System.out.println("Thursday");
        break;
      case 5:
        System.out.println("Friday");
        break;
      case 6:
        System.out.println("Saturday");
        break;
      case 7:
        System.out.println("Sunday");
        break;
    }
  }
}
```

#### Break and Continue statements
- **Break**: Used to jump out of a loop
- **Continue**: Used to break one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

#### Conditions in java:
- ##### Relational operators:
	- Less than: a < b
	- Less than or equal to: a <= b
	- Greater than: a > b
	- Greater than or equal to: a >= b
	- Equal to: a == b
	- Not Equal to: a != b

- ##### Logical Operators:
	- AND: &&
	- OR: ||
	- NOT: !


#### Explanation:
- **if-else**: Executes a block of code based on a condition.
- **for loop**: Repeats a block of code a specific number of times.
- **switch-case**: To choose between a number of alternatives for a given variable.
- **while loop**: Keeps executing as long as the condition is True

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



