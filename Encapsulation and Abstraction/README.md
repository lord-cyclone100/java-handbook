#### [Go Back ↩](../README.md)
## Java Handbook

<h1>Oops chapters - abstraction and encapsulation</h1>

### Encapsulation in Java

Encapsulation is a fundamental concept in Object-Oriented Programming (OOP) that bundles the data (variables) and the methods (functions) that operate on the data into a single unit, or class. It also restricts access to some of the object's components, making the object safer to use. In Java, encapsulation is implemented by making fields private and providing public getter and setter methods to access and update the values of these fields.

#### Example Program:

```java

public class Person {
    // Private fields (Encapsulation)
    private String name;
    private int age;
    
    // Constructor to initialize the object
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Getter method for name
    public String getName() {
        return name;
    }

    // Setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for age
    public int getAge() {
        return age;
    }

    // Setter method for age with validation
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Age cannot be negative!");
        }
    }
    
    // Display person's information
    public void displayInfo() {
        System.out.println("Name: " + getName());
        System.out.println("Age: " + getAge());
    }

    public static void main(String[] args) {
        // Create a new Person object
        Person person = new Person("Alice", 30);
        
        // Access data using getter methods
        person.displayInfo();
        
        // Modify data using setter methods
        person.setName("Bob");
        person.setAge(35);
        
        // Display updated info
        person.displayInfo();
    }
}

```

#### Explanation of Terms:

   - **Private Fields**: name and age are private to restrict direct access from outside the class.
   - **Getter and Setter Methods**: getName(), setName(), getAge(), and setAge() are public methods to get and set values for the private fields.
   - **Validation**: The setter method for age checks if the value is positive before setting it.

#### Abstraction in Java

Abstraction is the concept of hiding the complex implementation details and showing only the essential features of an object. In Java, abstraction can be achieved using abstract classes or interfaces. Abstract classes allow you to define methods with or without implementation, and subclasses must implement the abstract methods. Interfaces define a contract of methods that the implementing class must provide.

#### Example Program: Abstract Classes

```java

// Abstract class
abstract class Animal {
    // Abstract method (does not have a body)
    public abstract void sound();

    // Regular method (has a body)
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

// Concrete class (inherited from Animal)
class Dog extends Animal {
    // Providing implementation for the abstract method sound
    public void sound() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an object of the Dog class (which is a subclass of Animal)
        Animal myDog = new Dog();
        
        // Call the implemented methods
        myDog.sound();  // Output: The dog barks.
        myDog.eat();    // Output: This animal eats food.
    }
}

```

#### Explanation of Terms:

    - **Abstract Class**: Animal is an abstract class that defines an abstract method sound() without implementation. It also defines a regular method eat().
    - **Concrete Class**: Dog is a concrete class that provides an implementation for the sound() method.
    - **Abstraction**: The implementation details of the sound() method are hidden from the user of the Animal class. The user only interacts with the abstract class and calls the method sound() without needing to know how the sound is produced.

### Example Program: Interfaces

```java 

// Interface
interface Animal {
    void sound();  // Abstract method (no implementation)
}

// Concrete class implementing the interface
class Dog implements Animal {
    // Providing implementation for the sound method
    public void sound() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an object of the Dog class (which implements Animal)
        Animal myDog = new Dog();
        
        // Call the implemented method
        myDog.sound();  // Output: The dog barks.
    }
}

```
--- 

#### Explanation of Terms:

    - **Interface**: The Animal interface defines the abstract method sound() but does not provide its implementation.
    - **Implementing Class**: Dog implements the Animal interface and provides its own implementation for sound().
    - **Abstraction via Interface**: The sound() method is abstract in the interface, and the Dog class provides the specific implementation. This allows for more -    flexibility in how different classes can implement the same method.
