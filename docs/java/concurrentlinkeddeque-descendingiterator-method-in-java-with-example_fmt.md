# Java 中的 `ConcurrentLinkedDeque.descendingIterator()` 方法示例

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-descendingiterator-method-in-java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-descendingiterator-method-in-java-with-example/)

`java.util.ConcurrentLinkedDeque.descendingIterator()` 方法用于返回一个与 `ConcurrentLinkedDeque` 元素相同但顺序相反的迭代器。

## 语法

```java
Iterator iterate_value = Array_Deque.descendingIterator();
```

## 参数

该方法不接受任何参数。

## 返回值

该方法迭代 deque 的元素，并以相反的顺序返回值（迭代器）。

下面的程序说明了 `java.util.concurrent.ConcurrentLinkedDeque.descendingIterator()` 方法：

## 程序 1

```java
// Java code to illustrate descendingIterator()

import java.util.concurrent.*;
import java.util.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> de_que
            = new ConcurrentLinkedDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: " + de_que);

        // Creating a desc_iterator
        Iterator value = de_que.descendingIterator();

        // Displaying the values after iterating
        // through the ConcurrentLinkedDeque
        // in reverse order
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

## Output

```java
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Geeks
Geeks
To
Welcome
```

## 程序 2

```java
// Java code to illustrate descendingIterator()

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> de_que
            = new ConcurrentLinkedDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: " + de_que);

        // Creating a desc_iterator
        Iterator value = de_que.descendingIterator();

        // Displaying the values after iterating
        // through the ConcurrentLinkedDeque
        // in reverse order
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

## Output

```java
ConcurrentLinkedDeque: [10, 15, 30, 20, 5]
The iterator values are: 
5
20
30
15
10
```