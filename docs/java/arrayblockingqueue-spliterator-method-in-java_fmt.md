# Java 中的 `ArrayBlockingQueue` `spliterator()` 方法

> 原文：[https://www.geeksforgeeks.org/arrayblockingqueue-spliterator-method-in-java/](https://www.geeksforgeeks.org/arrayblockingqueue-spliterator-method-in-java/)

[`ArrayBlockingQueue`](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/) 的 [`spliterator()`](https://www.geeksforgeeks.org/arrayblockingqueue-spliterator-method-in-java/) 方法在 `ArrayBlockingQueue` 的元素上返回一个 [`Spliterator`](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)。返回的迭代器弱一致。在 Java 8 中，`Spliterator` 可以与 `Streams` 一起使用。`Spliterator` 也可以单独和批量遍历元素。

**语法：**

```java
public Spliterator<E> spliterator()
```

**返回值：** 这个方法在 `ArrayBlockingQueue` 中的元素上返回一个 `Spliterator`。

下面的程序说明了 `ArrayBlockingQueue` 类的 `spliterator()` 方法：

## 程序示例 1

```java
// Java Program Demonstrate spliterator()
// method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacityOfQueue = 7;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> Queue
            = new ArrayBlockingQueue<Integer>(capacityOfQueue);

        // Add element to ArrayBlockingQueue
        Queue.add(22);
        Queue.add(34);
        Queue.add(45);
        Queue.add(67);

        // create Spliterator of Queue
        // using spliterator() method
        Spliterator<Integer> numbers = Queue.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Numbers:");
        // forEachRemaining method of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出：**

```java
Size of Spliterator : 4
list of Numbers:
22
34
45
67
```

## 程序示例 2

```java
// Java Program Demonstrate spliterator()
// method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of ArrayBlockingQueue
        int capacityOfQueue = 7;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<String> QueueOfStrings
            = new ArrayBlockingQueue<String>(capacityOfQueue);

        // Add element to ArrayBlockingQueue
        QueueOfStrings.add("India");
        QueueOfStrings.add("Pakistan");
        QueueOfStrings.add("England");
        QueueOfStrings.add("China");
        QueueOfStrings.add("UAE");
        QueueOfStrings.add("Spain");

        // create Spliterator of QueueOfStrings
        // using spliterator() method
        Spliterator<String>
            listOfStrings = QueueOfStrings.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + listOfStrings.estimateSize());

        System.out.println("list of Country names:");

        // forEachRemaining method of Spliterator
        listOfStrings.forEachRemaining((str) -> print(str));
    }
    public static void print(String str)
    {
        System.out.println("Value = " + str);
    }
}
```

**输出：**

```java
Size of Spliterator : 6
list of Country names:
Value = India
Value = Pakistan
Value = England
Value = China
Value = UAE
Value = Spain
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#spliterator--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#spliterator--)