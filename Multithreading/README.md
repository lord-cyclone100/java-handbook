#### [Go Back ↩](../README.md)

## Multithreading in Java


### Introduction
Multithreading in Java allows concurrent execution of two or more parts of a program for maximum utilization of CPU. Each part of such a program is called a thread. It helps in performing multiple tasks simultaneously, improving application performance.

---

### Creating Threads
Threads in Java can be created in two ways: by extending the `Thread` class or by implementing the `Runnable` interface. Using `Thread` provides a direct way, while `Runnable` allows better flexibility by separating logic from the thread instance.

#### Method 1: Extending `Thread` Class
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
    
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}
```
**Explanation**
- **Extends `Thread`**: Defines a new thread by extending the `Thread` class.
- **Override `run()`**: The `run` method contains the logic to be executed in the new thread.
- **Call `start()`**: Initiates a separate thread execution.

#### Method 2: Implementing `Runnable` Interface
```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable thread is running...");
    }
    
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```
**Explanation**
- **Implements `Runnable`**: A more flexible way to define a thread.
- **Pass to `Thread` Constructor**: A `Runnable` instance is wrapped inside a `Thread` object.
- **Call `start()`**: Begins execution in a new thread.

---

### Thread Lifecycle
Threads go through multiple states from creation to termination. Understanding these states helps in better thread management and debugging.
1. **New**: Thread instance created but not started
2. **Runnable**: Ready to run but waiting for CPU
3. **Blocked**: Waiting for a resource
4. **Waiting**: Waiting indefinitely for another thread’s signal
5. **Timed Waiting**: Waiting for a specified time
6. **Terminated**: Execution completed

---

### Synchronization in Threads
When multiple threads access shared resources, inconsistencies can arise. Synchronization ensures that only one thread accesses a critical section at a time, preventing data corruption.

#### Using `synchronized` Keyword
```java
class SharedResource {
    synchronized void display(String msg) {
        System.out.print("[" + msg);
        try { Thread.sleep(1000); } catch (InterruptedException e) {}
        System.out.println("]");
    }
}

class MyThread extends Thread {
    SharedResource sr;
    String msg;
    
    MyThread(SharedResource sr, String msg) {
        this.sr = sr;
        this.msg = msg;
    }
    
    public void run() {
        sr.display(msg);
    }
    
    public static void main(String[] args) {
        SharedResource sr = new SharedResource();
        MyThread t1 = new MyThread(sr, "Hello");
        MyThread t2 = new MyThread(sr, "World");
        t1.start();
        t2.start();
    }
}
```
**Explanation**
- **`synchronized` Method**: Ensures only one thread can execute `display()` at a time.
- **Thread Execution**: Multiple threads attempt to execute `display()`, but synchronization prevents overlap.
- **Thread Sleep**: Simulates a delay to show synchronization effects.

---

### Best Practices
Following best practices helps in writing efficient and bug-free multithreaded programs.
- Minimize synchronization to avoid performance overhead
- Use `ExecutorService` for better thread management
- Prefer `Concurrent` collections over manually synchronized collections
- Always handle thread interruptions properly
- Avoid using `stop()`, `suspend()`, and `resume()` methods (deprecated due to thread safety issues)

---

### External Resources
- **Java Multithreading** → [Documentation](https://www.geeksforgeeks.org/multithreading-in-java/) || [Tutorial](https://www.restack.io/p/java-multithreading-answer)
- **Thread Synchronization** → [Documentation](https://www.geeksforgeeks.org/synchronization-in-java/) || [Tutorial](https://www.baeldung.com/java-thread-safety)
- **YouTube Tutorial** → [Java Multithreading (YouTube)](https://youtu.be/4aYvLz4E1Ts?feature=shared)

---
