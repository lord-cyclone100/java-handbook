#### [Go Back ↩](../README.md)

## Java OOPs: Package, Static, Singleton, In-built Methods

### Navigation
- [Package](#package)
- [Static Keyword](#static-keyword)
- [Singleton Class](#singleton-class)
- [In-built Methods](#in-built-methods)

---

### Package
#### What is a Package?
A package in Java is a namespace that organizes related classes and interfaces. It helps in avoiding name conflicts and provides access protection.

#### Creating a Package
```java
// Creating a package
package mypackage;

public class MyClass {
    public void display() {
        System.out.println("This is a class inside a package.");
    }
}
```
#### Using a Package
```java
// Importing a package
import mypackage.MyClass;

public class Main {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.display();
    }
}
```
**Explanation:**
- The `package` keyword is used to define a package that contains a group of related classes.
- The `import` statement is necessary to use a class from another package, making external code integration seamless.
- Packages help avoid naming conflicts by organizing classes logically and also provide access control, improving encapsulation.
- They make it easier to manage large projects by dividing functionality into modular components.

---

### Static Keyword
#### What is `static` in Java?
The `static` keyword in Java is used for memory management. It can be applied to variables, methods, blocks, and nested classes.

#### Static Variable & Method
```java
class StaticExample {
    static int count = 0;
    
    static void displayCount() {
        System.out.println("Count: " + count);
    }

    public static void main(String[] args) {
        count++;
        displayCount();
    }
}
```
**Explanation:**
- The `static` keyword makes a variable or method belong to the class rather than to instances of the class.
- `static int count` → This variable is shared among all objects of the class, meaning modifications affect all instances.
- `static void displayCount()` → This method can be accessed directly using the class name without needing an object.
- Static members reduce memory consumption since they are stored in a common memory area rather than being replicated for each instance.
- They are useful for utility functions and constants that should be accessible globally within a program.

---

### Singleton Class
#### What is a Singleton?
A Singleton ensures that only one instance of a class exists and provides a global access point.

#### Implementing a Singleton Class
```java
class Singleton {
    private static Singleton instance;
    
    private Singleton() { }
    
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}

public class Main {
    public static void main(String[] args) {
        Singleton obj1 = Singleton.getInstance();
        Singleton obj2 = Singleton.getInstance();
        System.out.println(obj1 == obj2); // true
    }
}
```
**Explanation:**
- The `private static Singleton instance;` variable ensures that only one instance of the class is created and stored.
- The constructor `private Singleton()` is private, preventing direct instantiation of the class from outside.
- `public static Singleton getInstance()` checks if an instance exists; if not, it creates one. This ensures only one instance is used throughout the application.
- The singleton pattern is useful in scenarios like database connections, logging, and configuration settings where a single point of control is necessary.

---

### In-built Methods
#### What are In-built Methods?
Java provides several built-in methods that simplify coding. Some common ones include:

#### String Methods
```java
public class StringMethods {
    public static void main(String[] args) {
        String str = "Hello World";
        System.out.println(str.length());       // 11
        System.out.println(str.toUpperCase()); // HELLO WORLD
        System.out.println(str.replace("World", "Java")); // Hello Java
    }
}
```
**Explanation:**
- `length()` returns the number of characters in a string, helping determine its size.
- `toUpperCase()` converts all characters in the string to uppercase, useful for case-insensitive operations.
- `replace()` replaces a specific substring with another, allowing for easy modifications of text-based data.
- These built-in methods enhance string manipulation without requiring manual implementation of complex logic.

#### Math Methods
```java
public class MathMethods {
    public static void main(String[] args) {
        System.out.println(Math.max(10, 20));  // 20
        System.out.println(Math.sqrt(25));     // 5.0
        System.out.println(Math.random());     // Random number
    }
}
```
**Explanation:**
- `Math.max(a, b)` returns the larger of two numbers, useful in comparison-based operations.
- `Math.sqrt(x)` calculates the square root of a given number, simplifying mathematical calculations.
- `Math.random()` generates a pseudo-random number between 0.0 and 1.0, often used in simulations and games.
- These methods save development time by providing reliable mathematical computations directly within Java's standard library.

---

### External Resources
- **Packages in Java** → [Documentation](https://www.geeksforgeeks.org/packages-in-java/) || [Tutorial](https://www.baeldung.com/java-packages)
- **Static in Java** → [Documentation](https://www.geeksforgeeks.org/static-keyword-java/) || [Tutorial](https://www.baeldung.com/java-static)
- **Singleton in Java** → [Documentation](https://www.geeksforgeeks.org/singleton-class-java/) || [Tutorial](https://www.baeldung.com/java-singleton)
- **Java In-built Methods** → [Documentation](https://www.geeksforgeeks.org/java-math-class/) || [Tutorial](https://www.baeldung.com/java-string)
- **YouTube Tutorial** → [Java OOPs Concepts](https://www.youtube.com/watch?v=_Ya6CN13t8k&ab_channel=KunalKushwaha)

