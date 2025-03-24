#### [Go Back ↩](../../README.md)

## Java Stream API

Java Stream API is used for processing collections of objects in a functional and declarative manner. Introduced in Java 8, it allows operations such as filtering, mapping, and reducing on data.

---

### 1. Creating Streams
```java
import java.util.Arrays;    
import java.util.List;
import java.util.stream.Stream;

public class StreamExample {
    public static void main(String[] args) {
        // Creating a Stream from a Collection
        List<String> list = Arrays.asList("Apple", "Banana", "Cherry");
        Stream<String> stream1 = list.stream();

        // Creating a Stream from an Array
        Stream<String> stream2 = Arrays.stream(new String[]{"Dog", "Cat", "Cow"});
    }
}
```
**Explanation:**
- Streams can be created from collections (`stream()`) and arrays (`Arrays.stream()`).
- Streams do not store data; they process it on demand.

---

### 2. Stream Operations
#### 2.1 Intermediate Operations
These operations transform a stream but do not terminate it.

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class IntermediateOperations {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David");
        
        List<String> filteredNames = names.stream()
            .filter(name -> name.startsWith("A")) // Filtering
            .map(String::toUpperCase) // Mapping
            .collect(Collectors.toList()); // Collecting to List
        
        System.out.println(filteredNames);
    }
}
```
**Explanation:**
- `.filter()` removes elements based on a condition.
- `.map()` transforms each element.
- `.collect()` gathers elements into a list.

---

#### 2.2 Terminal Operations
These operations produce a result or a side-effect and terminate the stream.

```java
import java.util.Arrays;
import java.util.List;

public class TerminalOperations {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        
        // Using forEach
        numbers.stream().forEach(System.out::println);
        
        // Using count
        long count = numbers.stream().count();
        System.out.println("Count: " + count);
    }
}
```
**Explanation:**
- `.forEach()` processes each element.
- `.count()` returns the number of elements in the stream.

---

### 3. Stream Reduction
```java
import java.util.Arrays;
import java.util.List;

public class StreamReduction {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        
        int sum = numbers.stream().reduce(0, Integer::sum);
        System.out.println("Sum: " + sum);
    }
}
```
**Explanation:**
- `.reduce()` aggregates stream elements into a single result.

---

### 4. Parallel Streams
```java
import java.util.Arrays;
import java.util.List;

public class ParallelStreams {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
        
        long count = numbers.parallelStream()
                            .filter(n -> n % 2 == 0)
                            .count();
        
        System.out.println("Count of even numbers: " + count);
    }
}
```
**Explanation:**
- `.parallelStream()` enables parallel execution for faster performance on large datasets.

---

### Best Practices
- Prefer `.stream()` for sequential processing and `.parallelStream()` only when working with large datasets.
- Avoid modifying data sources inside stream operations.
- Use `collect()` to transform streams into other data structures.
- Combine `.filter()` and `.map()` efficiently to avoid unnecessary computations.

---

### External Resources
- **Java Stream API** → [Documentation](https://www.geeksforgeeks.org/stream-in-java/) || [Tutorial](https://www.baeldung.com/java-8-streams)
- **YouTube Tutorial** → [Java Stream API (YouTube)](https://youtu.be/E10Q6-nWO9g?feature=shared)
