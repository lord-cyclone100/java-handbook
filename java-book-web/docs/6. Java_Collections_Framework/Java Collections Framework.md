#### [Go Back ↩](../README.md)

## Java Collections Framework

### Overview
The **Java Collections Framework (JCF)** provides a standardized architecture for managing and manipulating groups of objects. It includes interfaces, concrete implementations, and utility classes for efficient data handling.

---

### Key Interfaces

#### 1. Collection Interface (Root Interface)
- The base interface for all collection types.
- Extends **Iterable** for iteration capabilities.
- Sub Interfaces:
    - **List** (Ordered, allows duplicates)
    - **Set** (Unordered, unique elements)
    - **Queue** (FIFO structure)

#### 2. List Interface
- Ordered collection allowing duplicates.
- Implementations:
    - `ArrayList` - Dynamic array, fast random access.
    - `LinkedList` - Doubly linked list, efficient insertions/deletions.
    - `Vector` - Thread-safe dynamic array.
    - `Stack` - LIFO (Last In, First Out) structure.

#### 3. Set Interface
- Collection with unique elements (no duplicates).
- Implementations:
    - `LinkedHashSet` - Maintains insertion order.
    - `TreeSet` - Sorted collection backed by a Red-Black tree.

#### 4. Queue Interface
- FIFO (First In, First Out) ordering.
- Implementations:
    - `PriorityQueue` - Elements are ordered based on priority.
    - `ArrayDeque` - Resizable array-based double-ended queue.

#### 5. Deque Interface
- Double-ended queue, supports insertion and deletion from both ends.
- Implementations:
    - `ArrayDeque` - Array-based deque implementation.
    - `LinkedList` - Implements both **List** and **Deque**.

#### 6. Map Interface (Key-Value Pairs)
- Not a subtype of **Collection**; used for key-value storage.
- Implementations:
    - `HashMap` - Unordered key-value pairs, fast retrieval.
    - `LinkedHashMap` - Maintains insertion order.
    - `TreeMap` - Sorted key-value pairs using a Red-Black tree.
    - `Hashtable` - Synchronized version of **HashMap**.

#### 7. Iterator Interface
- Provides a way to traverse through collections.
- Methods:
    - `hasNext()` - Checks if there are more elements.
    - `next()` - Retrieves the next element.
    - `remove()` - Removes the last retrieved element.



### Common Methods in Collections

| Method | Description |
|--------|-------------|
| `add(E e)` | Adds an element to the collection. |
| `remove(Object o)` | Removes the specified element. |
| `size()` | Returns the number of elements. |
| `contains(Object o)` | Checks if an element exists. |
| `isEmpty()` | Checks if the collection is empty. |
| `iterator()` | Returns an iterator for iteration. |
| `clear()` | Removes all elements from the collection. |
| `toArray()` | Converts collection to an array. |
| `retainAll(Collection<?> c)` | Retains only elements present in another collection. |
| `removeAll(Collection<?> c)` | Removes all elements present in another collection. |

---

### Example Implementations

#### 1. List Example (ArrayList)
```java
import java.util.*;
public class ListExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Orange");
        System.out.println(list);
    }
}
```
**Explanation:**
- `ArrayList` is used to store an ordered collection of elements.
- `add()` method is used to add elements.
- `System.out.println(list)` prints the list contents.

#### 2. Map Example (HashMap)
```java
import java.util.*;
public class MapExample {
    public static void main(String[] args) {
        Map<Integer, String> map = new HashMap<>();
        map.put(1, "One");
        map.put(2, "Two");
        System.out.println(map);
    }
}
```
**Explanation:**
- `HashMap` stores key-value pairs.
- `put()` method is used to insert elements.
- `System.out.println(map)` prints the stored key-value pairs.

---

##### 3. Iterator Example
```java
import java.util.*;
public class IteratorExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Orange");

        Iterator<String> iterator = list.iterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```
**Explanation:**
- `iterator()` method retrieves an iterator for the list.
- `hasNext()` checks if there are more elements.
- `next()` retrieves and moves to the next element.

---

### Best Practices for Collections
- **Use Generics** - Avoid raw types to ensure type safety.
- **Use the Right Collection Type** - Choose based on performance needs (e.g., `ArrayList` vs `LinkedList`).
- **Handle Exceptions Properly** - Catch and handle exceptions like `ConcurrentModificationException`.
- **Avoid Memory Leaks** - Clear collections when no longer needed.
- **Optimize Iterations** - Use iterators and `forEach` loops efficiently.

---

### External Resources
- **Java Collections Framework** → [Documentation](https://www.geeksforgeeks.org/collections-in-java-2/) || [Tutorial](https://www.baeldung.com/java-collections)
- **YouTube Tutorial** → [Java Collections Framework (YouTube)](https://youtu.be/9ogGan-R1pc?feature=shared)
