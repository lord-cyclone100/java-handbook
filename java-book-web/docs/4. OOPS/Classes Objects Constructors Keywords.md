#### [Go Back ↩](../README.md)
# OOPS : Classes & Objects, Constructors, Keywords

## Navigation
- **[Classes & Objects](#classes-objects)**
- **[Constructors](#constructors)**
- **[Keywords](#keywords)**

---

## Classes & Objects
### Overview
In Java, a **class** is a blueprint for creating objects. It defines properties (fields) and behaviors (methods). An **object** is an instance of a class that contains actual values stored in memory.

### Code Example
```java
class Car {
    String brand;
    int speed;

    void display() {
        System.out.println("Brand: " + brand + ", Speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car(); // Object creation
        myCar.brand = "Tesla";
        myCar.speed = 120;
        myCar.display();
    }
}
```

### Explanation
- `Car` is a class with two fields (`brand`, `speed`) and a method `display()`.
- `myCar` is an **object** of `Car`, initialized and assigned values.
- `display()` prints object properties.

**[Classes & Objects]** → [Documentation](https://www.geeksforgeeks.org/classes-objects-java/) || [Tutorial](https://www.baeldung.com/java-classes-objects)

**YouTube Tutorial** → [Watch Here](https://youtu.be/BSVKUk58K6U?feature=shared)

---

## Constructors
### Overview
A **constructor** is a special method used to initialize objects. It has the same name as the class and does not have a return type.

### Code Example
```java
class Car {
    String brand;
    int speed;

    // Constructor
    Car(String b, int s) {
        brand = b;
        speed = s;
    }

    void display() {
        System.out.println("Brand: " + brand + ", Speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Tesla", 120); // Constructor invocation
        myCar.display();
    }
}
```

### Explanation
- A **constructor** (`Car(String b, int s)`) initializes object properties.
- Objects are instantiated with initial values using the constructor.
- Constructors allow automatic assignment of values at object creation.

**[Constructors]** → [Documentation](https://www.geeksforgeeks.org/constructors-in-java/) || [Tutorial](https://www.baeldung.com/java-constructors)

**YouTube Tutorial** → [Watch Here](https://youtu.be/BSVKUk58K6U?feature=shared)

---

## Keywords
### Overview
Java has several **keywords** that are reserved for special purposes. Some commonly used ones include:
- `class` - Defines a class.
- `new` - Creates a new object.
- `this` - Refers to the current instance of a class.
- `static` - Defines a static member.
- `final` - Used to declare constants or prevent inheritance.

### Code Example
```java
class Example {
    static final int VALUE = 100; // final constant
    
    void show() {
        System.out.println("Static Final Value: " + VALUE);
    }
}

public class Main {
    public static void main(String[] args) {
        Example obj = new Example(); // new keyword
        obj.show();
    }
}
```

### Explanation
- `static final` defines a constant `VALUE`.
- `new` keyword creates an instance of `Example`.
- `show()` displays the constant value.

**[Keywords]** → [Documentation](https://www.geeksforgeeks.org/java-keywords/) || [Tutorial](https://www.w3schools.com/java/java_ref_keywords.asp)

**YouTube Tutorial** → [Watch Here](https://youtu.be/BSVKUk58K6U?feature=shared)
