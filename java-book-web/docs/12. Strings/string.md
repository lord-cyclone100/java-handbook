#### [Go Back ↩](../README.md)

## String in Java
In Java, a `String` is an immutable sequence of characters. It is represented by the `String` class, which is part of `java.lang` package.

### Creating a String
```java
String str1 = "Hello";
String str2 = new String("World");
```
## Commonly Used String Methods

| Method | Description |
|--------|-------------|
| `length()` | Returns the length of the string. |
| `charAt(index)` | Returns the character at the specified index. |
| `substring(beginIndex, endIndex)` | Extracts a portion of the string. |
| `toUpperCase()` | Converts all characters to uppercase. |
| `toLowerCase()` | Converts all characters to lowercase. |
| `trim()` | Removes whitespace from both ends of the string. |
| `replace(oldChar, newChar)` | Replaces occurrences of a character. |
| `equals(anotherString)` | Compares two strings for equality. |
| `equalsIgnoreCase(anotherString)` | Compares two strings ignoring case differences. |
| `startsWith(prefix)` | Checks if the string starts with a given prefix. |
| `endsWith(suffix)` | Checks if the string ends with a given suffix. |
| `indexOf(ch)` | Returns the index of the first occurrence of a character. |
| `lastIndexOf(ch)` | Returns the index of the last occurrence of a character. |
| `concat(anotherString)` | Concatenates two strings. |

### Example:
```java
String str = "  Hello Java!  ";
System.out.println(str.trim()); // Output: "Hello Java!"
System.out.println(str.toUpperCase()); // Output: "  HELLO JAVA!  "
```

---

## StringBuilder Class in Java
Unlike `String`, `StringBuilder` is mutable, meaning it allows modification of its content without creating new objects.

### Creating a StringBuilder
```java
StringBuilder sb = new StringBuilder("Hello");
```

### Commonly Used StringBuilder Methods

| Method | Description |
|--------|-------------|
| `append(str)` | Adds a string to the end. |
| `insert(index, str)` | Inserts a string at a specified index. |
| `replace(start, end, str)` | Replaces characters between start and end index with a new string. |
| `delete(start, end)` | Deletes characters between start and end index. |
| `reverse()` | Reverses the string. |
| `length()` | Returns the length of the sequence. |
| `charAt(index)` | Returns the character at the specified index. |
| `setCharAt(index, ch)` | Modifies the character at the given index. |
| `toString()` | Converts `StringBuilder` to a `String`. |

### Example:
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb.toString()); // Output: "Hello World"

sb.reverse();
System.out.println(sb.toString()); // Output: "dlroW olleH"
```

## StringBuilder vs String
- Use `String` when immutability is required.
- Use `StringBuilder` when frequent modifications are needed for better performance.
- Use `StringBuffer` if thread safety is a concern.


