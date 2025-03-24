#### [Go Back ↩](../README.md)

## Java Concurrency

Java Concurrency is essential for executing multiple tasks in parallel, improving performance and responsiveness in applications. It allows programs to efficiently use multi-core processors, handle asynchronous tasks, and perform parallel computations.

### Key Concepts

### 1. Threads and Runnable

Threads are the fundamental units of execution in Java. They enable parallel processing and improve efficiency. Java provides the `Thread` class and `Runnable` interface to create and manage threads.

#### Creating a Thread Using `Thread` Class

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); // Starts the thread
    }
}
```

**Explanation:**
- Extends the `Thread` class and overrides `run()`.
- Calls `start()` to initiate execution in a separate thread.

#### Creating a Thread Using `Runnable` Interface

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

**Explanation:**
- Implements `Runnable` interface and defines `run()`.
- `Thread` is instantiated using `Runnable` and started using `start()`.

### 2. Thread Lifecycle

Threads transition through different states during execution, such as new, runnable, blocked, waiting, timed waiting, and terminated. Understanding these states helps in managing thread behavior effectively.

```java
class LifecycleExample extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }

    public static void main(String[] args) {
        LifecycleExample t1 = new LifecycleExample();
        System.out.println("Thread state before start: " + t1.getState());
        t1.start();
        System.out.println("Thread state after start: " + t1.getState());
    }
}
```

**Explanation:**
- Demonstrates how to retrieve a thread’s state before and after calling `start()`.
- Helps understand the lifecycle transitions of a thread.

### 3. Executors Framework

The Executors framework provides a higher-level API for managing thread pools efficiently. Instead of manually creating threads, `Executors` manage and optimize thread allocation.

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ExecutorExample {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(3);
        Runnable task = () -> System.out.println("Executing task in: " + Thread.currentThread().getName());

        for (int i = 0; i < 5; i++) {
            executor.execute(task);
        }

        executor.shutdown();
    }
}
```

**Explanation:**
- Uses `Executors.newFixedThreadPool(3)` to create a thread pool.
- Submits tasks to the executor, which manages the threads efficiently.

### 4. Synchronization and Locks

To prevent race conditions, Java provides mechanisms like `synchronized` blocks and `ReentrantLock` to ensure thread-safe execution.

#### Using `synchronized` Method

```java
class SharedResource {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}
```

**Explanation:**
- `synchronized` ensures only one thread accesses `increment()` at a time.
- Prevents race conditions by enforcing mutual exclusion.

#### Using `ReentrantLock`

```java
import java.util.concurrent.locks.ReentrantLock;

class SharedLockResource {
    private int count = 0;
    private ReentrantLock lock = new ReentrantLock();

    public void increment() {
        lock.lock();
        try {
            count++;
        } finally {
            lock.unlock();
        }
    }

    public int getCount() {
        return count;
    }
}
```

**Explanation:**
- `ReentrantLock` provides finer control over locking and unlocking.
- Ensures safe access to shared resources without using `synchronized`.

### 5. Callable and Future

`Callable` allows tasks to return results, unlike `Runnable`. `Future` is used to retrieve results once execution is complete.

```java
import java.util.concurrent.Callable;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class CallableExample {
    public static void main(String[] args) throws Exception {
        ExecutorService executor = Executors.newSingleThreadExecutor();
        Callable<Integer> task = () -> {
            Thread.sleep(1000);
            return 42;
        };

        Future<Integer> result = executor.submit(task);
        System.out.println("Result: " + result.get());
        executor.shutdown();
    }
}
```

**Explanation:**
- Uses `Callable` to return a result after execution.
- `Future.get()` retrieves the result once execution completes.

### 6. Thread Communication (wait & notify)

Threads can communicate using `wait()` and `notify()`, allowing better coordination between dependent tasks.

```java
class SharedResource {
    private boolean ready = false;

    public synchronized void waitForSignal() throws InterruptedException {
        while (!ready) {
            wait();
        }
        System.out.println("Thread notified and proceeding...");
    }

    public synchronized void sendSignal() {
        ready = true;
        notify();
    }
}
```

**Explanation:**
- `wait()` causes a thread to wait until `notify()` is called.
- `notify()` wakes up waiting threads to continue execution.

## Best Practices for Concurrency

1. **Use Executors Instead of Creating Threads Manually** - Managing thread pools is more efficient.
2. **Minimize Use of `synchronized` Blocks** - Use `Lock` and `Concurrent` utilities where applicable.
3. **Avoid Deadlocks** - Ensure proper ordering of locks and avoid circular dependencies.
4. **Use Thread-Safe Collections** - Utilize `ConcurrentHashMap`, `CopyOnWriteArrayList`, and `BlockingQueue`.
5. **Leverage Atomic Variables** - `AtomicInteger` and `AtomicLong` reduce the need for synchronization.

## External Resources

- **Java Concurrency** → [Documentation](https://www.geeksforgeeks.org/java-util-concurrent-package/) || [Tutorial](https://www.baeldung.com/java-concurrency)
- **Thread Synchronization** → [Documentation](https://www.geeksforgeeks.org/synchronization-in-java/) || [Tutorial](https://www.tutorialspoint.com/java/java_thread_synchronization.htm)
- **YouTube Tutorial** → [Java Concurrency (YouTube)](https://youtu.be/4aYvLz4E1Ts?feature=shared)

