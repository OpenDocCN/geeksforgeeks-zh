# Java 中的 BlockingQueue offer() 方法示例

> 原文：[https://www.geeksforgeeks.org/blockingqueue-offer-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-offer-method-in-java-with-examples/)

`BlockingQueue` 接口的 `offer()` 方法有两种：
**注：** `BlockingQueue` 的 `offer()` 方法继承了 Java 中的 `Queue` 类。

## offer(E e, long timeout, TimeUnit unit)

`BlockingQueue` 的 `offer(E e, long timeout, TimeUnit unit)` 方法，如果队列未满，则在该阻塞队列的尾部插入作为参数传递给方法的元素。如果阻塞队列已满，它将等待指定时间，直到空间变得可用。指定的等待时间和时间单位将作为 `offer()` 方法的参数给出。所以它会等到 `BlockingQueue` 移除一些元素的时候，这样这个方法就可以向 `BlockingQueue` 添加元素。

**语法：**

```java
public boolean offer(E e, long timeout, TimeUnit unit) throws InterruptedException
```

**参数：** 该方法接受三个参数：
*   `e` – 要插入阻塞队列的元素。
*   `timeout` – `offer` 方法等待插入新元素的时间（当队列已满时）。
*   `unit` – `timeout` 参数的时间单位。

**返回值：** 如果元素插入成功，该方法返回 `true`。否则，如果在空间可用之前经过了指定的等待时间，它将返回 `false`。

**异常：** 此方法抛出以下异常：
*   `NullPointerException` – 如果指定的元素为 `null`。
*   `InterruptedException` – 如果在等待时线程被中断。

下面的程序说明了 `BlockingQueue` 类的 `offer(E e, long timeout, TimeUnit unit)` 方法：

**程序 1：**

```java
// Java Program Demonstrate
// offer(Element e, long timeout, TimeUnit unit)
// method of BlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    // Main method
    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<Integer>
            BQ = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add 5 elements to BlockingQueue having
        // Timeout in seconds with value 5 secs in
        // offer(Element e, long timeout, TimeUnit unit)
        System.out.println("adding 32673821 "
                           + BQ.offer(32673821,
                                      5,
                                      TimeUnit.SECONDS));
        System.out.println("adding 88527183: "
                           + BQ.offer(88527183,
                                      5,
                                      TimeUnit.SECONDS));
        System.out.println("adding 431278539: "
                           + BQ.offer(431278539,
                                      5,
                                      TimeUnit.SECONDS));
        System.out.println("adding 351278693: "
                           + BQ.offer(351278693,
                                      5,
                                      TimeUnit.SECONDS));
        System.out.println("adding 647264: "
                           + BQ.offer(647264,
                                      5,
                                      TimeUnit.SECONDS));

        // print the elements of queue
        System.out.println("list of numbers of queue:"
                           + BQ);

        // now queue is full check remaining capacity of queue
        System.out.println("Empty spaces of queue : "
                           + BQ.remainingCapacity());

        // try to add more Integer
        boolean response = BQ.offer(2893476,
                                    5,
                                    TimeUnit.SECONDS);
        System.out.println("Adding new Integer 2893476 is successful: "
                           + response);
    }
}
```

**输出：**

```java
adding 32673821 true
adding 88527183: true
adding 431278539: true
adding 351278693: true
adding 647264: false
list of numbers of queue:[32673821, 88527183, 431278539, 351278693]
Empty spaces of queue : 0
Adding new Integer 2893476 is successful: false
```

**程序 2：**

```java
// Java Program Demonstrate
// offer(Element e, long timeout, TimeUnit unit)
// method of BlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<Integer>
            BQ = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add elements to BlockingQueue having
        // Timeout in seconds with value 5 secs in
        // offer(Element e, long timeout, TimeUnit unit)
        System.out.println("Adding 283239 in Queue :"
                           + BQ.offer(283239,
                                      5,
                                      TimeUnit.SECONDS));

        // try to put null value in offer method
        try {

            System.out.println("Adding null in Queue: "
                               + BQ.offer(null,
                                          5,
                                          TimeUnit.SECONDS));
        }
        catch (Exception e) {

            // print error details
            System.out.println("Exception: " + e);
        }

        // print elements of queue
        System.out.println("Items in Queue are "
                           + BQ);
    }
}
```

**输出：**

```java
Adding 283239 in Queue :true
Exception: java.lang.NullPointerException
Items in Queue are [283239]
```

## offer(E e)

`BlockingQueue` 的 `offer(E e)` 方法，如果队列有空间（即队列未满），则在该阻塞队列的尾部插入作为参数传递的元素 `E`。如果队列已满，则调用 `offer()` 方法不会产生任何效果，因为阻塞队列将阻塞要插入的元素。`offer()` 方法在向 `BlockingQueue` 添加操作成功时返回 `true`，如果该队列已满，则返回 `false`。此方法优于 `add()` 方法，因为当队列已满时 `add` 方法会引发错误，但在这种情况下 `offer()` 方法会返回 `false`。

**语法：**

```java
public boolean offer(E e)
```

**参数：** 该方法取一个强制参数 `e`，该参数是要插入到 `LinkedBlockingQueue` 中的元素。

**返回值：** 如果元素插入成功，该方法返回 `true`。否则返回 `false`。

**异常：** 如果指定的元素为 `null`，方法抛出 `NullPointerException`。

以下程序说明 `BlockingQueue` 类的 `offer()` 方法：

**程序 1：**

```java
// Java Program Demonstrate
// offer(Element e)
// method of BlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<String>
            BQ = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to BlockingQueue using offer
        BQ.offer("dean");
        BQ.offer("kevin");
        BQ.offer("sam");
        BQ.offer("jack");

        // print the elements of queue
        System.out.println("list of names of queue:");
        System.out.println(BQ);
    }
}
```

**输出：**

```java
list of names of queue:
[dean, kevin, sam, jack]
```

**程序 2：**

## Java BlockingQueue offer() 方法示例

```java
// Java Program Demonstrate
// offer(Element e)
// method of BlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<Integer>
            BQ = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add element to BlockingQueue using offer
        BQ.offer(34567);
        BQ.offer(45678);
        BQ.offer(98323);
        BQ.offer(93758);

        // print the elements of queue
        System.out.println("list of numbers of queue:");
        System.out.println(BQ);

        // now queue is full check remaining capacity of queue
        System.out.println("Empty spaces of queue : "
                           + BQ.remainingCapacity());

        // try to add extra Integer
        boolean response = BQ.offer(2893476);

        System.out.println("Adding new Integer 2893476 is successful: "
                           + response);

        response = BQ.offer(456751);

        System.out.println("Adding new Integer 456751 is successful: "
                           + response);
    }
}
```

**Output**

```
list of numbers of queue:
[34567, 45678, 98323, 93758]
Empty spaces of queue : 0
Adding new Integer 2893476 is successful: false
Adding new Integer 456751 is successful: false
```

## offer() 方法异常处理示例

```java
// Java Program Demonstrate offer(E e)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element using offer() method
        BQ.offer("Karan");

        // try to put null value in offer method
        try {
            BQ.offer(null);
        }
        catch (Exception e) {
            // print error details
            System.out.println("Exception: " + e);
        }

        // print elements of queue
        System.out.println("Items in Queue are "
                           + BQ);
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException
Items in Queue are [Karan]
```

**参考:**

*   [`https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#offer(E)`](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#offer(E))
*   [`https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#offer(E, long, java.util.concurrent.TimeUnit)`](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#offer(E, long, java.util.concurrent.TimeUnit))