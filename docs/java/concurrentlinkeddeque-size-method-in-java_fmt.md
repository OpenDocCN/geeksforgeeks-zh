# ConcurrentLinkedDeque的size()方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-size-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-size-method-in-java/)

`ConcurrentLinkedDeque`类的`size()`方法用于查找`ConcurrentLinkedDeque`容器中存在的元素数量。换句话说，此方法返回容器的当前容量。此方法返回的值是整型的，如果容器包含的元素多于整数的最大值，则此方法返回整数的最大值，即`Integer.MAX_VALUE`。

**语法：**
```java
ConcurrentLinkedDeque.size()
```

**参数：** 该方法不接受任何参数。
**返回值：** 这个方法返回一个整数值，它是`ConcurrentLinkedDeque`容器的当前大小。

以下程序说明了`ConcurrentLinkedDeque`的`size()`方法：

```java
// Java Program to demonstrate the
// size of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        // Adding elements to the collection
        cld.addFirst(12);
        cld.addFirst(70);
        cld.addFirst(1009);
        cld.addFirst(475);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Calculate size
        int size = cld.size();

        System.out.println("Size of the collection is: "
                           + size);
    }
}
```

**输出：**
```java
ConcurrentLinkedDeque: [475, 1009, 70, 12]
Size of the collection is: 4
```

**注意：** 与Java中的其他集合不同，由于这些Deque的异步性质，该方法不会在恒定时间内执行`ConcurrentLinkedDeque`的大小计算操作，并且在执行该方法的过程中大小可能会发生变化，在这种情况下返回的结果会不准确。这种方法在并发应用程序中通常不是很有用。

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#size())