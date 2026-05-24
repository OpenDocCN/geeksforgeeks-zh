# 如何在 Java 中获取当前运行线程的 Id？

> 原文：[https://www.geeksforgeeks.org/how-to-get-the-id-of-a-current-running-thread-in-java/](https://www.geeksforgeeks.org/how-to-get-the-id-of-a-current-running-thread-in-java/)

[`Thread`](https://www.geeksforgeeks.org/java-lang-thread-class-java/) 类的 `getId()` 方法返回被调用线程的标识符。线程标识是创建该线程时生成的长正数。线程标识是唯一的，并且在其生存期内保持不变。当一个线程被终止时，这个线程标识可以被重用。

Java 允许在线程的帮助下并行执行程序的不同部分。Java 中的多线程是通过扩展 `Thread` 类或实现 `Runnable` 接口来实现的。由于 Java 中不允许多重继承，所以建议实现 [`Runnable`](https://www.geeksforgeeks.org/runnable-interface-in-java/) 接口来创建线程，这样如果需要，实现 `Runnable` 接口的类可以扩展一些其他类。在本文中，我们已经演示了创建线程的两种方法。第一种方法通过扩展 `Thread` 类显示线程创建，第二种方法通过实现 `Runnable` 接口显示线程创建。

**声明：**
```java
public long getId()
```

**返回值：** 这个方法返回一个线程的 ID。

## 方法 1

以下是通过[扩展 `Thread` 类](https://www.geeksforgeeks.org/multithreading-in-java/)来创建线程的步骤。

1.  `ThreadDemo1` 类扩展了 `Thread` 类并覆盖了 `Thread` 类的 `run()` 方法。
2.  在 `run()` 方法中，我们使用 `currentThread().getName()` 方法获取调用 `run()` 方法的当前线程的名称。
3.  我们使用 `currentThread().getId()` 方法获取调用 `run()` 方法的当前线程的 Id。
4.  在 `main()` 方法中，创建了两个 `ThreadDemo1` 类的实例。
5.  `t1` 和 `t2` 是两个调用 `start()` 方法的线程。
6.  调用 `start()` 方法默认会调用 `run()` 方法。
7.  [`join()`](https://www.geeksforgeeks.org/joining-threads-in-java/) 方法用于防止 `t2` 在 `t1` 完成之前运行。
8.  一旦 `t1` 完成，`t2` 就会被执行。

### 示例

```java
// Java program to get the id of a thread
import java.util.*;
public class ThreadDemo1 extends Thread {
    public void run()
    {
        // gets the name of current thread
        System.out.println(
            "Current Thread Name: "
            + Thread.currentThread().getName());

        // gets the ID of the current thread
        System.out.println(
            "Current Thread ID: "
            + Thread.currentThread().getId());
    }
    public static void main(String[] args)
        throws InterruptedException
    {
        Scanner s = new Scanner(System.in);

        // creating first thread
        ThreadDemo1 t1 = new ThreadDemo1();

        // creating second thread
        ThreadDemo1 t2 = new ThreadDemo1();

        // Starting the thread
        t1.start();
        t2.start();

        // t2 does not start execution until t1 completes
        // execution
        t1.join();
    }
}
```

### 输出

```java
Current Thread Name: Thread-0
Current Thread Name: Thread-1
Current Thread ID: 11
Current Thread ID: 12
```

## 方法 2

在第二种方法中，通过实现 `Runnable` 接口来创建线程。

1.  `ThreadDemo2` 类实现了 `Runnable` 接口并覆盖了 `run()` 方法。
2.  创建了一个 `ThreadDemo2` 类的可运行实例 `t`。
3.  通过将 `Runnable` 实例作为第一个参数，线程名称作为第二个参数，创建了两个 `Thread` 类的实例。
4.  在两个线程上调用 `start()` 方法。
5.  `start()` 方法默认调用 `run()` 方法。

### 示例

```java
// Java program to get the id of a thread
public class ThreadDemo2 implements Runnable {
    public void run()
    {
        // gets the name of current thread
        System.out.println(
            "Current Thread Name: "
            + Thread.currentThread().getName());

        // gets the ID of the current thread
        System.out.println(
            "Current Thread ID: "
            + Thread.currentThread().getId());
    }
    public static void main(String[] args)
    {
          // Runnable target
        ThreadDemo2 t = new ThreadDemo2();

        // create threads
        Thread t1 = new Thread(t, "First Thread");
        Thread t2 = new Thread(t, "Second Thread");

        // start threads
        t1.start();
        t2.start();
    }
}
```

### 输出

```java
Current Thread Name: First Thread
Current Thread Name: Second Thread
Current Thread ID: 11
Current Thread ID: 12
```

**注意：** 第二种方法的输出可能会有所不同，因为它不是[同步的](https://www.geeksforgeeks.org/synchronized-in-java/)，并且线程是并发执行的。因此，线程名称或线程 id 的打印顺序可能会有所不同。为了防止这个问题，我们在第一种方法中使用了 [`join()`](https://www.geeksforgeeks.org/joining-threads-in-java/) 方法。如果要保持打印输出的顺序，那么用户可以使用 `join()` 方法。