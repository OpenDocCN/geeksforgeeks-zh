# Java 中的 `ConcurrentLinkedDeque.spliterator()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-spliterator-method-in-java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-spliterator-method-in-java-with-examples/)

## 方法描述

`ConcurrentLinkedDeque` 的 `spliterator()` 方法返回一个在 `ConcurrentLinkedDeque` 元素上的 `Spliterator`。返回的迭代器是弱一致的。在 Java 8 中，该 `Spliterator` 可以与 Streams 一起使用。它也可以单独或用于批量遍历元素。

## 语法

```java
public Spliterator<E> spliterator()
```

## 返回值

该方法在 `ConcurrentLinkedDeque` 的元素上返回一个 `Spliterator`。

## 示例程序

下面的程序说明了 `ConcurrentLinkedDeque` 的 `spliterator()` 方法：

### 程序 1

```java
// Java Program to demonstrate spliterator()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CBD
            = new ConcurrentLinkedDeque<Integer>();

        // Add elements
        CBD.add(22);
        CBD.add(34);
        CBD.add(45);
        CBD.add(67);

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<Integer> numbers
            = CBD.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Numbers:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining(
            (n) -> System.out.println(n));
    }
}
```

**输出：**

```java
Size of Spliterator : 9223372036854775807
list of Numbers:
22
34
45
67
```

### 程序 2

```java
// Java Program to demonstrate spliterator()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CBD
            = new ConcurrentLinkedDeque<String>();

        // Add numbers to front of ConcurrentLinkedDeque
        CBD.add("Geeks");
        CBD.add("forGeeks");
        CBD.add("A");
        CBD.add("Computer");
        CBD.add("Portal");

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<String> numbers
            = CBD.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Strings:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining(
            (n) -> System.out.println(n));
    }
}
```

**输出：**

```java
Size of Spliterator : 9223372036854775807
list of Strings:
Geeks
forGeeks
A
Computer
Portal
```