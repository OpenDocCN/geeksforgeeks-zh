# Java中的ConcurrentLinkedDeque peekFirst()方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-peekfirst-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-peekfirst-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.peekFirst()`是Java中的一个内置方法，在不移除它的情况下检索这个双端队列的第一个元素。如果目标双端队列为空，该功能返回`null`。

## 语法

```java
Conn_Linked_Deque.peekFirst()
```

## 参数

该功能不接受任何参数。

## 返回值

函数返回这个双端队列中出现的第一个元素，当双端队列为空时返回`null`。

下面的程序说明了`peekFirst()`方法：

## 程序1

该程序涉及到带有整数元素的双端队列。

```java
// Java Program Demonstrate peekFirst()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld =
                    new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(110);
        cld.addFirst(55);
        cld.addFirst(76);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Displaying the first element
        System.out.println("First Element in"
                   + "the LinkedDeque: " + cld.peekFirst());
    }
}
```

**Output:**

```java
Elements inthe LinkedDeque: [76, 55, 110, 12]
First Element inthe LinkedDeque: 76
```

## 程序2

本程序涉及到带有字符串元素的双端队列。

```java
// Java Program Demonstrate peekFirst()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                           new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Gfg");
        cld.addFirst("GeeksforGeeks");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Displaying the First element
        System.out.println("First Element in"
                       + "the LinkedDeque: " + cld.peekFirst());
    }
}
```

**Output:**

```java
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg, GFG]
First Element inthe LinkedDeque: Geeks
```

## 参考

`https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#peekFirst--`