# Java 中的 `LinkedBlockingDeque.spliterator()` 方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-spliterator-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-spliterator-method-in-java/)

`LinkedBlockingDeque` 的 `spliterator()` 方法返回 `LinkedBlockingDeque` 元素上的一个 `Spliterator`。返回的迭代器弱一致。在 Java 8 中，拆分器可以与 Streams 一起使用。分割器也可以单独和批量遍历元素。

## 语法

```java
public Spliterator<E> spliterator()
```

## 返回值

这个方法返回一个 `Spliterator`，它位于 `LinkedBlockingDeque` 的元素上。

下面的程序说明了 `LinkedBlockingDeque` 的 `spliterator()` 方法：

## 程序 1

```java
// Java Program to demonstrate spliterator()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add elements
        LBD.add(22);
        LBD.add(34);
        LBD.add(45);
        LBD.add(67);

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<Integer> numbers = LBD.spliterator();

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

## 程序 2

```java
// Java Program to demonstrate spliterator()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to front of LinkedBlockingDeque
        LBD.add("Geeks");
        LBD.add("forGeeks");
        LBD.add("A");
        LBD.add("Computer");
        LBD.add("Portal");

        // create Spliterator of Deque
        // using spliterator() method
        Spliterator<String> numbers = LBD.spliterator();

        // getExactSize of Spliterator
        System.out.println("Size of Spliterator : "
                           + numbers.estimateSize());

        System.out.println("list of Strings:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出：**

```java
Size of Spliterator : 5
list of Strings:
Geeks
forGeeks
A
Computer
Portal
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#spliterator--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#spliterator--)