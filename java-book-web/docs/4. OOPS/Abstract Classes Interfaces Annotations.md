#### [Go Back ↩](../README.md)

## Abstract Classes, Interfaces, and Annotations

### [🔝 Back to Navigation](#)

### Abstract Classes

Abstract classes in Java provide a blueprint for other classes. They can contain abstract methods (without implementation) as well as concrete methods (with implementation). Abstract classes cannot be instantiated.

```java
abstract class Animal {
    abstract void makeSound();
    
    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Output: Bark
        dog.sleep(); // Output: Sleeping...
    }
}
```

#### Explanation
- The `Animal` class is abstract and cannot be instantiated.
- It defines an abstract method `makeSound()` that must be implemented by any subclass.
- It also has a concrete method `sleep()` that all subclasses can use.
- `Dog` extends `Animal` and provides an implementation for `makeSound()`.

### Interfaces

Interfaces define a contract that implementing classes must follow. They only contain method signatures and constants.

```java
interface Animal {
    void makeSound();
}

class Cat implements Animal {
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Cat cat = new Cat();
        cat.makeSound(); // Output: Meow
    }
}
```

#### Explanation
- The `Animal` interface defines a method `makeSound()`.
- The `Cat` class implements `Animal` and provides an implementation for `makeSound()`.
- Unlike abstract classes, interfaces do not provide method implementations (before Java 8).

### Annotations

Annotations provide metadata about the code and do not affect program logic. Common built-in annotations include `@Override`, `@Deprecated`, and `@FunctionalInterface`.

```java
class Parent {
    void show() {
        System.out.println("Parent show method");
    }
}

class Child extends Parent {
    @Override
    void show() {
        System.out.println("Child show method");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent obj = new Child();
        obj.show(); // Output: Child show method
    }
}
```

#### Explanation
- `@Override` ensures that `show()` in `Child` correctly overrides the method from `Parent`.
- If the method signature doesn’t match, the compiler throws an error.
- Other annotations like `@Deprecated` indicate obsolete methods, while `@FunctionalInterface` is used for functional interfaces.

### Best Practices
- Use abstract classes when you need to provide some common functionality along with abstract methods.
- Use interfaces when you need to define behavior that multiple classes can implement independently.
- Use annotations to provide metadata, enforce constraints, and improve code readability.

### External Resources
- **Abstract Classes** → [Documentation](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html) || [Tutorial](https://www.baeldung.com/java-abstract-class)
- **Interfaces** → [Documentation](https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html) || [Tutorial](https://www.baeldung.com/java-interfaces)
- **Annotations** → [Documentation](https://docs.oracle.com/javase/tutorial/java/annotations/) || [Tutorial](https://www.baeldung.com/java-annotations)
- **YouTube Tutorial** → [Java Abstract Classes, Interfaces & Annotations (YouTube)](https://youtu.be/rgHZa7-Dibg?feature=shared)
