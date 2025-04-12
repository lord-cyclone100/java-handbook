#### [Go Back ↩](../README.md)


## Understanding Java String Pool and String Interning

Java handles strings a little differently than many other programming languages, thanks to something called the **String Pool**. This optimization technique makes string handling more efficient in terms of **memory usage** and **performance**.


## What is the String Pool?

The **String Pool** is a special memory region in the Java heap where **string literals** are stored.

When you create a string like this:

```java
String a = "hello";
String b = "hello";
```

Java will **not** create two separate `String` objects. Instead, both `a` and `b` will point to the **same object in the String Pool**.

When a string literal is created, the JVM checks if it already exists in the pool.If it does, a reference to the pooled instance is returned.If not, the string is added to the pool.

✔️ This saves memory.  
✔️ It also allows for quick equality checks using `==`.

## String Pool vs `new String()`
```java
String s1 = "test";
String s2 = new String("test");

System.out.println(s1 == s2);        // false (different references)
System.out.println(s1.equals(s2));   // true  (same content)
```

Use `.intern()` to bring `s2` to the pool:
-

```java
System.out.println(s1 == s2.intern());  // true
```

## String Interning

**Interning** means storing only one copy of each distinct string value, which must be immutable.

### Interning in Action

You can force a string to be added to the pool using the `intern()` method:

```java
String x = new String("world");
String y = x.intern();

String z = "world";

System.out.println(y == z); // true
```

Even though `x` was created with `new` (so it lives outside the pool), `y` becomes a reference to the **pooled** version of `"world"`.



## Literal vs. New Keyword

| Declaration                 | In String Pool? | Memory Saved? |
|----------------------------|-----------------|----------------|
| `String s1 = "hello";`     | Yes             | ✅ Yes         |
| `String s2 = new String("hello");` | No (until interned) | ❌ No          |


## Key Points

- The String Pool exists to optimize memory.
- Literals go directly into the pool.
- Use `.intern()` to add runtime strings to the pool.
- `==` compares references, `equals()` compares content.

