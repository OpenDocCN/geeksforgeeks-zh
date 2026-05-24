# 多线程 Java 程序中如何使用锁？

> 原文：[https://www.geeksforgeeks.org/how-to-use-locks-in-multi-threaded-java-program/](https://www.geeksforgeeks.org/how-to-use-locks-in-multi-threaded-java-program/)

锁可能是比标准同步块更灵活和复杂的线程同步机制。锁可以是用于控制多个线程对共享资源的访问的工具。通常，锁提供对共享资源的独占访问：一次只有一个线程可以获取锁，每个访问共享资源的人都需要先获取锁。然而，有些锁可能允许对共享资源的并发访问，比如读写锁的读锁。

```java
// Example of lock interface
Lock lock = new ReentrantLock();
lock.lock();

// critical section 
lock.unlock();
```

## `Lock` 接口中的方法

`Lock` 接口中有某些方法。我们将查看那些以及它们的修饰符：

| **修饰符** | **描述** |
| :--- | :--- |
| `void` | `lock()` – 如果锁可用，则获取锁；如果锁不可用，线程将被阻塞直到锁被释放。 |
| | `lockInterruptibly()` – 类似于 `lock()`，但除非线程被中断，否则会获取锁。 |
| | `unlock()` – 顾名思义，这就是释放锁的实例。 |
| `Condition` | `newCondition()` – 它只是返回一个新的 `Condition` 实例。 |
| `boolean` | `tryLock()` – 它试图立即获取锁，如果锁定成功则返回 `true`。 |
| | `tryLock(long time, TimeUnit unit)` – 通常与 `tryLock()` 几乎相同，除了在放弃尝试获取锁之前会等待给定的超时时间。 |

## 锁的实现

让我们看看如何在 Java 中实现一些锁：

### 1. `ReadWriteLock()`

```java
ReadWriteLock readWriteLock = new ReentrantReadWriteLock();

readWriteLock.readLock().lock();

// ....

// ....

readWriteLock.readLock().unlock();

readWriteLock.writeLock().lock();

// only one writer can enter this section,
    // and only if no threads are currently reading.

readWriteLock.writeLock().unlock();
```

下面是 `ReadWriteLock()` 方法的实现：

```java
// Implementation of ReadWriteLock in Java
import java.io.*;
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;
class GFG<O> {

    private final ReadWriteLock readWriteLock
        = new ReentrantReadWriteLock();
    private final Lock writeLock
        = readWriteLock.writeLock();
    private final Lock readLock = readWriteLock.readLock();
    private final List<O> list = new ArrayList<>();

    // setElement function sets
    // i.e., write the element to the thread
    public void setElement(O o)
    {
        // acquire the thread for writing
        writeLock.lock();
        try {
            list.add(o);
            System.out.println(
                "Element by thread "
                + Thread.currentThread().getName()
                + " is added");
        }
        finally {
            // To unlock the acquired write thread
            writeLock.unlock();
        }
    }

    // getElement function prints
    // i.e., read the element from the thread
    public O getElement(int i)
    {
        // acquire the thread for reading
        readLock.lock();
        try {
            System.out.println(
                "Elements by thread "
                + Thread.currentThread().getName()
                + " is printed");
            return list.get(i);
        }
        finally {
            // To unlock the acquired read thread
            readLock.unlock();
        }
    }
    public static void main(String[] args)
    {
        GFG<String> gfg = new GFG<>();

        gfg.setElement("Hi");
        gfg.setElement("Hey");
        gfg.setElement("Hello");

        System.out.println("Printing the last element : "
                           + gfg.getElement(2));
    }
}
```

**输出：**

```
Element by thread main is added
Element by thread main is added
Element by thread main is added
Elements by thread main is printed
Printing the last element : Hello
```

### 2. `ReentrantLock()`

```java
public class lockImplement {
    //...
    ReentrantLock lock = new ReentrantLock();
    int counter = 0;

    public void testing() {
        lock.lock();
        try {
            // Critical section here
            count++;
        } finally {
            lock.unlock();
        }
    }
    //...
}
```

下面是 `ReentrantLock()` 方法的实现：

```java
// Java code to illustrate Reentrant Lock
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

class SharedResource {
    private final Lock lock = new ReentrantLock();
    private int counter = 0;

    public void increment() {
        lock.lock();
        try {
            counter++;
            System.out.println(Thread.currentThread().getName() 
                + " - Counter value after increment: " + counter);
        } finally {
            lock.unlock();
        }
    }

    public int getCounter() {
        return counter;
    }
}

class Worker implements Runnable {
    private SharedResource resource;

    public Worker(SharedResource resource) {
        this.resource = resource;
    }

    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            resource.increment();
        }
    }
}

public class ReentrantLockExample {
    public static void main(String[] args) {
        SharedResource resource = new SharedResource();
        Thread t1 = new Thread(new Worker(resource), "Thread-1");
        Thread t2 = new Thread(new Worker(resource), "Thread-2");

        t1.start();
        t2.start();
    }
}
```

**输出：**

```
Thread-1 - Counter value after increment: 1
Thread-1 - Counter value after increment: 2
Thread-1 - Counter value after increment: 3
Thread-1 - Counter value after increment: 4
Thread-1 - Counter value after increment: 5
Thread-2 - Counter value after increment: 6
Thread-2 - Counter value after increment: 7
Thread-2 - Counter value after increment: 8
Thread-2 - Counter value after increment: 9
Thread-2 - Counter value after increment: 10
```

**注意：** 由于睡眠调用，程序可能无法在在线 IDE 上工作。