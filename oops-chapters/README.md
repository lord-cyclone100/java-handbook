# Object-Oriented Programming (OOP) Concepts

This document provides a collection of chapters covering fundamental **Object-Oriented Programming (OOP)** concepts. Each chapter explains a core OOP concept and includes code examples in multiple programming languages: **Java**.

## Table of Contents
1. [Chapter 1: Introduction to OOP](#chapter-1-introduction-to-oop)
2. [Chapter 2: Encapsulation](#chapter-2-encapsulation)
3. [Chapter 3: Inheritance](#chapter-3-inheritance)
4. [Chapter 4: Polymorphism](#chapter-4-polymorphism)
5. [Chapter 5: Abstraction](#chapter-5-abstraction)

---

## Chapter 1: Introduction to OOP

### What is OOP?
Object-Oriented Programming (OOP) is a programming paradigm that uses objects to represent real-world entities. OOP makes code more reusable, modular, and easier to maintain.

### Why OOP is Important:
- **Modularity**: Code is divided into smaller, manageable pieces (objects).
- **Reusability**: Objects can be reused in different programs.
- **Maintainability**: Code is easier to maintain and update.

### Key Concepts of OOP:
1. **Encapsulation**: Hiding the internal state of an object and providing access through methods.
2. **Inheritance**: Allowing objects to inherit properties and behaviors from other objects.
3. **Polymorphism**: Allowing objects of different types to be treated as instances of the same class.
4. **Abstraction**: Hiding unnecessary details and showing only essential features.

---

## Chapter 2: Encapsulation

### What is Encapsulation?
Encapsulation is the concept of bundling data (attributes) and the methods (functions) that operate on that data into a single unit (class). It also refers to restricting access to some of an object’s components to protect its integrity.

### Why Encapsulation is Important:
- **Data Protection**: Prevents unauthorized access to an object's internal state.<br/>
- **Control Over Data**: Provides a controlled way to access and modify data.

### Code Examples:

#### Java:

```java

lass Person {
    private String name;  // Private attribute

    public String getName() {
        return name;  // Getter method
    }

    public void setName(String name) {
        this.name = name;  // Setter method
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("Alice");
        System.out.println(person.getName());  // Output: Alice
    }
}

```
---

## Chapter 3: Inheritance

### What is Inheritance?

Inheritance allows one class (child class) to inherit properties and methods from another class (parent class). It promotes code reuse and establishes a hierarchy between classes.

### Why Inheritance is Useful:

**Code Reusability**: Child classes can use methods and properties from parent classes.<br/>
**Hierarchical Classification**: Helps in organizing related classes

### Code Examples:


#### Java:

```java

class Animal {
    public void speak() {
        System.out.println("Animal speaks");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("Woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.speak();  // Inherited method
        dog.bark();   // Dog-specific method
    }
}

```
---


### Chapter 4: Polymorphism

### What is Polymorphism?

Polymorphism allows objects of different classes to be treated as instances of the same class. This provides flexibility in the code and allows different behaviors for the same method call based on the object's type.

### Why Polymorphism is Helpful:

**Flexibility**: Different object types can be used interchangeably.<br/>
**Dynamic Behavior**: The method behavior can differ depending on the object type.

#### Code Examples:

#### Java:

```java

class Dog {
    public void speak() {
        System.out.println("Woof!");
    }
}

class Cat {
    public void speak() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        Cat cat = new Cat();

        dog.speak();  // Output: Woof!
        cat.speak();  // Output: Meow!
    }
}

```
---

## Chapter 5: Abstraction

### What is Abstraction?

Abstraction is the concept of hiding the complex implementation details and only exposing the necessary features. It simplifies the interaction with objects by focusing on their essential behaviors.

### Why Abstraction is Important:

**Simplifies Usage**: Only essential features are exposed.<br/>
**Reduces Complexity**: Hides unnecessary implementation details.

### Code Examples:

#### Java:

```java

abstract class Animal {
    public abstract void speak();
}

class Dog extends Animal {
    public void speak() {
        System.out.println("Woof!");
    }
}

class Cat extends Animal {
    public void speak() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();
        
        dog.speak();  // Output: Woof!
        cat.speak();  // Output: Meow!
    }
}

```
---

### Conclusion:
This README.md file introduces the core concepts of Object-Oriented Programming (OOP) and provides code examples in Java, Python, C++, and JavaScript. The goal is to help developers learn and apply OOP principles through clear explanations and practical examples.
