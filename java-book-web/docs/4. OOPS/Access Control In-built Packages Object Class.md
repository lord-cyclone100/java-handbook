#### [Go Back ↩](../README.md)

## Java Exception Handling


### Navigation
[Access Control](#access-control) | [In-built Packages](#in-built-packages) | [Object Class](#object-class)

---

### Access Control
Access control in Java defines the visibility and accessibility of classes, methods, and variables. It is managed using four access modifiers:

- **private**: Accessible only within the same class.
- **default (package-private)**: Accessible within the same package.
- **protected**: Accessible within the same package and subclasses.
- **public**: Accessible from anywhere.

#### Example:
```java
class Parent {
    private int privateVar = 10;
    int defaultVar = 20;
    protected int protectedVar = 30;
    public int publicVar = 40;
}

public class AccessModifierDemo {
    public static void main(String[] args) {
        Parent obj = new Parent();
        // System.out.println(obj.privateVar); // Error: private access
        System.out.println(obj.defaultVar); // Accessible (same package)
        System.out.println(obj.protectedVar); // Accessible (same package)
        System.out.println(obj.publicVar); // Accessible (anywhere)
    }
}
```
**Explanation:** Here, `privateVar` is inaccessible outside the class, while other variables have different levels of accessibility based on their modifiers.

---

### In-built Packages
Java provides a vast collection of built-in packages for performing various tasks, such as I/O operations, utility functions, and concurrency management. Some common packages include:

- `java.lang` (Automatically imported, contains core classes like `String`, `Math`, `Object`)
- `java.util` (Contains utility classes like `ArrayList`, `HashMap`, `Collections`)
- `java.io` (Contains classes for input and output operations)
- `java.net` (Contains classes for network programming)

#### Example:
```java
import java.util.ArrayList;

public class BuiltInPackageDemo {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        System.out.println(list);
    }
}
```
**Explanation:** The `java.util.ArrayList` class is used to create a dynamic array.

---

### Object Class
The `Object` class is the root class of the Java class hierarchy. Every class in Java implicitly extends `Object` unless explicitly specified otherwise. It provides several key methods:

- `toString()`: Returns a string representation of the object.
- `equals(Object obj)`: Checks if two objects are equal.
- `hashCode()`: Returns the hash code of an object.
- `clone()`: Creates a copy of an object (requires implementing `Cloneable`).

#### Example:
```java
class Student {
    String name;
    int id;
    
    Student(String name, int id) {
        this.name = name;
        this.id = id;
    }

    @Override
    public String toString() {
        return "Student{name='" + name + "', id=" + id + "}";
    }
}

public class ObjectClassDemo {
    public static void main(String[] args) {
        Student s1 = new Student("Alice", 101);
        System.out.println(s1.toString()); // Implicit call to toString()
    }
}
```
**Explanation:** The `toString()` method is overridden to provide a meaningful representation of the `Student` object.

---

### External Resources
- **Access Control** → [Documentation](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html) || [Tutorial](https://www.geeksforgeeks.org/access-modifiers-java/)
- **In-built Packages** → [Documentation](https://docs.oracle.com/javase/tutorial/java/package/index.html) || [Tutorial](https://www.baeldung.com/java-packages)
- **Object Class** → [Documentation](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html) || [Tutorial](https://www.tutorialspoint.com/java/java_object_class.htm)
- **YouTube Tutorial** → [Java Access Modifiers (YouTube)](https://youtu.be/W145DXs8fFg?feature=shared)  
