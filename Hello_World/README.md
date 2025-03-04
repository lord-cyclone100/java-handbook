#### [Go Back ↩](../README.md)

# Hello World Program

A "Hello, World!" program is a fundamental example used in programming to display the text "Hello, World!" on the screen. It is often the first program written by beginners to understand the basic syntax of a programming language and ensure the development environment is correctly configured. The program is simple yet significant, as it introduces key concepts like printing output, syntax rules, and compilation or interpretation processes. It is widely used across various languages, from C, Python, Java, to JavaScript and many others. Despite its simplicity, it represents an essential first step in a programmer’s learning journey.


### The Program

This is how you create the basic Hello World program in Java.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
###### Lets now understand each of the terms used in this program

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `public`

This is an access modifier that makes the class and method accessible from anywhere in the program. In this case, public ensures that the `main()` method can be executed by the Java Virtual Machine (JVM).

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `class`

This keyword defines a class in Java, which is a blueprint for objects.
Here, `HelloWorld` is the name of the class. The filename must match the class name `(HelloWorld.java)`.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `static`

A keyword that means the method belongs to the class rather than an instance of the class. `main()` is static so that it can be called by JVM without creating an object of the class.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `void`

This keyword specifies that the method does not return any value. The `main()` method runs the program but does not return any data.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `main`

This is the entry point of a Java program. The JVM starts execution from the main() method.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `String[] args`

String[] is an array of Strings, and args is the name of the array. It is used to pass command-line arguments to the program.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `System`

This is a built-in class in Java that provides access to system-related functions.

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `out`

This is a static member of the System class, representing the standard output stream (console).

#### <img src="https://www.pinclipart.com/picdir/big/53-534873_vector-steam-java-developer-java-icon-png-clipart.png" height="25" width="25"> `println()`

This method prints text to the console and moves to the next line. `"Hello, World!"` is the output in this case.

##### We shall learn about these concepts in detail in the upcoming chapters