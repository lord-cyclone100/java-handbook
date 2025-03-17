#### [Go Back ↩](../README.md)

## OOP Principles

### Navigation

- [Inheritance](#inheritance)
- [Polymorphism](#polymorphism)
- [Encapsulation](#encapsulation)
- [Abstraction](#abstraction)

---

### Inheritance

Inheritance is a fundamental OOP concept that allows one class (child or subclass) to acquire properties and behaviors (methods) from another class (parent or superclass). This enables code reusability, hierarchical classification, and easy maintenance.

For example:

```java
class Parent {
    void display() {
        System.out.println("This is the parent class.");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("This is the child class.");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Child obj = new Child();
        obj.display(); // Calls inherited method from Parent
        obj.show(); // Calls Child class method
    }
}
```

**Explanation:**
- The `Child` class extends `Parent`, which means it inherits the `display()` method from the parent class.
- The child class can access both its own methods and the inherited methods from the parent class.
- This allows reusability of code, reducing redundancy and improving structure.
- If needed, the child class can override the parent class methods to provide a specialized implementation.

---

### Polymorphism

Polymorphism allows methods to have multiple forms. It enables flexibility and scalability by allowing the same method name to function differently based on the object or parameter type.

Polymorphism is implemented through:

#### Method Overloading (Compile-time Polymorphism)

This allows multiple methods with the same name but different parameters, enabling functionality to adapt based on input.

```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }
    
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class OverloadingExample {
    public static void main(String[] args) {
        MathOperations obj = new MathOperations();
        System.out.println(obj.add(5, 10)); // Calls first method
        System.out.println(obj.add(5, 10, 15)); // Calls second method
    }
}
```

**Explanation:**
- The `add()` method is overloaded, meaning the same method name exists with different parameters.
- The appropriate method is selected based on the number and type of arguments passed.
- This helps in making code more intuitive and easy to understand.

#### Method Overriding (Runtime Polymorphism)

Method overriding allows a subclass to provide a specific implementation of a method already defined in its parent class. This is essential for achieving dynamic method dispatch.

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}

public class OverridingExample {
    public static void main(String[] args) {
        Animal myAnimal = new Dog();
        myAnimal.makeSound(); // Calls overridden method in Dog
    }
}
```

**Explanation:**
- The `Dog` class overrides the `makeSound()` method from `Animal`.
- When we create an `Animal` reference and assign it a `Dog` object (`new Dog()`), the overridden method in `Dog` is executed at runtime.
- This helps in implementing real-world behaviors, such as different animals having different sounds.

---

### Encapsulation

Encapsulation is the practice of bundling data (variables) and methods that operate on that data into a single unit, restricting direct access to data by making fields private and exposing them through public getter and setter methods.

```java
class Person {
    private String name;
    
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}

public class EncapsulationExample {
    public static void main(String[] args) {
        Person p = new Person();
        p.setName("John Doe");
        System.out.println("Name: " + p.getName());
    }
}
```

**Explanation:**
- The `name` variable is private and cannot be accessed directly outside the `Person` class.
- The getter (`getName()`) and setter (`setName()`) methods provide controlled access, ensuring data integrity.
- This principle helps in securing sensitive data and maintaining encapsulation boundaries.

---

### Abstraction

Abstraction is the process of hiding implementation details and exposing only essential features. This simplifies complexity and enhances maintainability.

#### Abstract Class Example

```java
abstract class Vehicle {
    abstract void start();
}

class Car extends Vehicle {
    void start() {
        System.out.println("Car starts with a key.");
    }
}

public class AbstractionExample {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start(); // Calls implemented method in Car
    }
}
```

**Explanation:**
- `Vehicle` is an abstract class that declares an abstract method `start()`, meaning its implementation is left for the subclass (`Car`).
- The `Car` class provides the specific implementation of `start()`.
- This promotes modularity by separating what an object does from how it does it.

#### Interface Example

```java
interface Animal {
    void makeSound();
}

class Cat implements Animal {
    public void makeSound() {
        System.out.println("Cat meows");
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        Animal myCat = new Cat();
        myCat.makeSound(); // Calls implemented method in Cat
    }
}
```

**Explanation:**
- `Animal` is an interface that enforces the implementation of `makeSound()` in `Cat`.
- Interfaces allow multiple classes to implement common behavior while maintaining independent implementations.

---

### External Resources

- **Inheritance & Polymorphism** → [Documentation](https://www.geeksforgeeks.org/inheritance-in-java/) || [Tutorial](https://www.baeldung.com/java-inheritance)
- **Encapsulation & Abstraction** → [Documentation](https://www.tutorialspoint.com/java/java_encapsulation.htm) || [Tutorial](https://www.baeldung.com/java-abstract-class)
- **YouTube Tutorial** → [OOP Concepts (YouTube)](https://www.youtube.com/watch?v=46T2wD3IuhM&ab_channel=KunalKushwaha)
