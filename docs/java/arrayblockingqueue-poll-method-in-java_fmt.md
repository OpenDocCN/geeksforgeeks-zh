# Java 中的 ArrayBlockingQueue poll()方法

> 原文: [https://www.geeksforgeeks.org/arrayblockingqueue-poll-method-in-java/](https://www.geeksforgeeks.org/arrayblockingqueue-poll-method-in-java/)

[`ArrayBlockingQueue`](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [`ArrayBlockingQueue`](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

根据传递的参数数量，有两种`poll()`方法。

## 1. `poll()` 方法

`poll()`方法**检索并移除此队列的头部元素**。如果队列为空，则方法将返回`null`。

**语法:**

```java
public E poll()
```

**返回值:** 该方法从该队列的头部返回元素，如果该队列为空，则返回`null`。

下面的程序说明了`ArrayBlockingQueue`的`poll()`方法。

**程序 1:**

```java
/*
 * Program Demonstrate poll() method of ArrayBlockingQueue.
 */

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = new
               ArrayBlockingQueue<Integer>(capacity);

        // Add elements to ArrayBlockingQueue
        queue.offer(423);
        queue.offer(233);
        queue.offer(356);

        // print elements
        System.out.println("Queue Contains" + queue);

        // try to poll  elements
        System.out.println("Removing From head: " +
                               queue.poll());
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: " +
                               queue.poll());
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: " +
                               queue.poll());
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: " +
                               queue.poll());
        System.out.println("Queue Contains" + queue);
    }
}
```

**输出:**

```java
Queue Contains[423, 233, 356]
Removing From head: 423
Queue Contains[233, 356]
Removing From head: 233
Queue Contains[356]
Removing From head: 356
Queue Contains[]
Removing From head: null
Queue Contains[]
```

**程序 2:**

```java
/*
 * Program Demonstrate poll() method of ArrayBlockingQueue.
 */

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    // Create a User Object with name and age as an attribute
    public class User {

        public String name;
        public String age;
        User(String name, String age)
        {
            this.name = name;
            this.age = age;
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.pollMethodExample();
    }

    // Method to give example of contains function
    public void pollMethodExample()
    {

        // Define the capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<User> queue =
               new ArrayBlockingQueue<User>(capacity);

        // Create user objects
        User user1 = new User("Aman", "24");
        User user3 = new User("Sanjeet", "25");

        // Add Objects to ArrayBlockingQueue
        queue.offer(user1);
        queue.offer(user3);

        // Poll users from queue
        User user = queue.poll();
        System.out.println("removing user having name = "
                                    + user.name);
        user = queue.poll();
        System.out.println("removing user having name = "
                                    + user.name);

        // Now queue is empty
        // Try to remove it will return null
        user = queue.poll();
        System.out.println("removing user having name = "
                                         + user);
    }
}
```

**输出:**

```java
removing user having name = Aman
removing user having name = Sanjeet
removing user having name = null
```

## 2. `poll(long timeout, TimeUnit unit)` 方法

`poll(long timeout, TimeUnit unit)`方法**检索并移除此队列的头部元素**。如果队列为空，它将等待指定的时间，直到有元素可用。

**语法:**

```java
public E poll(long timeout, TimeUnit unit) throws InterruptedException
```

**参数:** 该方法取两个参数:

*   `timeout` (long) – 放弃前需要等待多长时间，单位为`unit`。
*   `unit` (TimeUnit) - 决定如何解释`timeout`参数的时间单位。

**返回值:** 该方法返回此队列的头部，如果在元素可用之前经过了指定的等待时间，则返回`null`。
**异常:** 该方法会抛出`InterruptedException`如果在等待时被中断。

下面的程序说明了`ArrayBlockingQueue`的`poll(long timeout, TimeUnit unit)`方法。

```java
/*
 * Program Demonstrate offer(E e, long timeout, TimeUnit unit)
 * method of ArrayBlockingQueue.
 */

import java.util.concurrent.ArrayBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
                           throws InterruptedException
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue =
            new ArrayBlockingQueue<Integer>(capacity);

        // Add elements to ArrayBlockingQueue
        queue.offer(423);
        queue.offer(233);
        queue.offer(356);

        // Print elements
        System.out.println("Queue Contains" + queue);

        // Try to poll  elements
        System.out.println("Removing From head: "
                  + queue.poll(10, TimeUnit.SECONDS));
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: "
                  + queue.poll(10, TimeUnit.SECONDS));
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: " +
                    queue.poll(10, TimeUnit.SECONDS));
        System.out.println("Queue Contains" + queue);
        System.out.println("Removing From head: " +
                   queue.poll(10, TimeUnit.SECONDS));
    }
}
```

**输出:**

```java
Queue Contains[423, 233, 356]
Removing From head: 423
Queue Contains[233, 356]
Removing From head: 233
Queue Contains[356]
Removing From head: 356
Queue Contains[]
Removing From head: null
```

**参考:**
[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#poll()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#poll())