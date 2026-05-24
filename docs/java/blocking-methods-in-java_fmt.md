# Java 中的阻塞方法

> 原文：[https://www.geeksforgeeks.org/blocking-methods-in-java/](https://www.geeksforgeeks.org/blocking-methods-in-java/)

Java 中的阻塞方法是阻塞线程直到其操作完成的一组特定方法。因此，它们将不得不阻塞当前线程，直到满足完成任务的条件。因为在本质上，这些方法是阻塞的，所以被称为阻塞方法。例如，`InputStream.read()`方法会阻塞，直到所有 `InputStream` 数据都被完全读取。下面是一些最常见的 Java 阻塞方法：

1.  `wait()`：等待事件调度线程执行代码。
2.  `InputStream.read()`：它会阻塞，直到输入数据可用、抛出异常或检测到流的结尾。
3.  `ServerSocket.accept()`：监听传入的 Java 套接字连接，并在连接建立前阻塞。
4.  `CountDownLatch.await()`：使当前线程等待，直到锁存器计数为零，除非线程被中断。

阻塞方法有几个缺点：

*   阻塞技术对系统的可扩展性构成巨大威胁。一个经典的阻塞解决方案包括减少阻塞的方法，并使用多线程来服务多个客户。
*   设计是最重要的方面，因为即使一个多线到达某个点，一个设计不良的系统也只能支持数百或数千个线程，因为 JVM 线程的数量是有限的。

## 实施

在下面的示例中，在执行第一个 `print` 语句后，程序将被第二个 `print` 语句阻塞，直到控制台中输入一些字符。然后单击回车，因为 `read()` 会阻塞该方法，直到某些输入可读为止。

### 例 1

```java
// Java Program to illustrate Blocking methods

// Importing all input output classes
import java.io.*;

// Class
class GFG {

    // main driver method
    public static void main(String args[]) throws FileNotFoundException, IOException {
        // Print statement
        System.out.println("GFG");

        int result;
        result = System.in.read();

        // Print statement
        System.out.println("Geeks for Geeks");
    }
}
```

**输出**

```java
GFG
Geeks for Geeks
```

### 例 2

在这个例子中，当一个线程在开始工作之前需要等待其他线程时，使用 `CountDownLatch.await()`。`countDown()` 方法减少计数，`await()` 方法阻塞，直到计数等于 0。

```java
// Java Program to illustrate Blocking methods

// Importing all input output classes
import java.io.*;
// Importing concurrent CountDownLatch class
// from java.util package
import java.util.concurrent.CountDownLatch;

// Class
class GFG {

    // Main driver method
    public static void main(String args[]) throws InterruptedException {
        // Let us create task that is going to wait
        // for five threads before it starts
        CountDownLatch latch = new CountDownLatch(4);

        // Creating threads of Person type
        // Custom parameter inputs
        Person p1 = new Person(1500, latch, "PERSON-1");
        Person p2 = new Person(2500, latch, "PERSON-2");
        Person p3 = new Person(3500, latch, "PERSON-3");
        Person p4 = new Person(4500, latch, "PERSON-4");
        Person p5 = new Person(5500, latch, "PERSON-5");

        // Starting the thread
        // using the start() method
        p1.start();
        p2.start();
        p3.start();
        p4.start();
        p5.start();

        // Waiting for the four threads
        // using the latch.await() method
        latch.await();

        // Main thread has started
        System.out.println(Thread.currentThread().getName() + " has finished his work");
    }
}

// Class 2
// Helper class extending Thread class
// To represent threads for which the main thread waits
class Person extends Thread {
    // Member variables of this class
    private int delay;
    private CountDownLatch latch;

    // Method of this class
    public Person(int delay, CountDownLatch latch, String name) {
        // super refers to parent class
        super(name);

        // This keyword refers to current object itself
        this.delay = delay;
        this.latch = latch;
    }

    @Override
    public void run() {
        // Try block to check for exceptions
        try {
            Thread.sleep(delay);
            latch.countDown();

            // Print the current thread by getting its name
            // using the getName() method
            // of whose work is completed
            System.out.println(Thread.currentThread().getName() + " has finished his work");
        }

        // Catch block to handle the exception
        catch (InterruptedException e) {
            // Print the line number where exception occured
            // using the printStackTrace() method
            e.printStackTrace();
        }
    }
}
```

**输出**

```java
PERSON-1 has finished his work
PERSON-2 has finished his work
PERSON-3 has finished his work
PERSON-4 has finished his work
main has finished his work
PERSON-5 has finished his work
```