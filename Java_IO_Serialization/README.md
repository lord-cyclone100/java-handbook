## Java Serialization & Deserialization

### Serialization
Serialization in Java is the process of converting an object into a byte stream so that it can be stored in a file, transmitted over a network, or persisted in some other way. Java provides built-in support for serialization through the `java.io.Serializable` interface.

### Deserialization
Deserialization is the process of reconstructing an object from a previously serialized byte stream. This allows objects to be restored to their original state, making it useful for data persistence and communication between systems. During deserialization, the class definition must be available in the runtime environment to reconstruct the object.

---

### Implementing Serialization

```java
import java.io.*;

class Person implements Serializable {
    private static final long serialVersionUID = 1L;
    String name;
    int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

public class SerializationDemo {
    public static void main(String[] args) {
        Person person = new Person("John Doe", 30);
        
        try (FileOutputStream fileOut = new FileOutputStream("person.ser");
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(person);
            System.out.println("Object has been serialized");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Explanation
- The `Person` class implements `Serializable`, allowing its instances to be serialized.
- `serialVersionUID` ensures class consistency during deserialization.
- `FileOutputStream` and `ObjectOutputStream` are used to write the object to a file (`person.ser`).

---

### Implementing Deserialization

```java
import java.io.*;

public class DeserializationDemo {
    public static void main(String[] args) {
        try (FileInputStream fileIn = new FileInputStream("person.ser");
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            Person person = (Person) in.readObject();
            System.out.println("Object has been deserialized");
            System.out.println("Name: " + person.name + ", Age: " + person.age);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

### Explanation
- `FileInputStream` and `ObjectInputStream` read the serialized object from `person.ser`.
- The object is cast back to the `Person` class.
- If the class definition changes and `serialVersionUID` is not properly managed, deserialization may fail.

---

### Important Considerations
- **Transient Fields**: Fields marked as `transient` are **not serialized**.
- **serialVersionUID**: Helps maintain version control for serialized objects.
- **Externalizable Interface**: Used for custom serialization logic.

---

### External Resources
- **Serialization in Java** → [Documentation](https://www.geeksforgeeks.org/serialization-in-java/) || [Tutorial](https://www.baeldung.com/java-serialization)
- **Deserialization in Java** → [Documentation](https://www.geeksforgeeks.org/serialization-in-java/) || [Tutorial](https://www.baeldung.com/java-serialization)
- **YouTube Tutorial** → [Serialization & Deserialization](https://youtu.be/b-KLxooxih4?feature=shared)
