# Java 中的 ConcurrentLinkedDeque peekLast()方法

> 原文：[`https://www.geeksforgeeks.org/concurrentlinkeddeque-peeklast-method-in-java/`](https://www.geeksforgeeks.org/concurrentlinkeddeque-peeklast-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.peekLast()`是 Java 中的一个内置方法，
检索这个 deque 容器的最后一个元素，而不移除它。如果目标为空，该功能返回`null`。

## 语法

```java
Conn_Linked_Deque.peekLast()
```

## 参数

函数不接受任何参数。

## 返回值

函数返回`this`德格中存在的最后一个元素，当德格为空时返回`null`。

下面的程序说明了`peekLast()`方法的使用：

## 程序 1

该程序涉及到带有`Integer`元素的德克尔。

```java
// Java Program Demonstrate peekLast()
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

        // Displaying the last element
        System.out.println("Last Element in"
                    + "the LinkedDeque: " + cld.peekLast());
    }
}
```

**Output:**

```java
Elements inthe LinkedDeque: [76, 55, 110, 12]
Last Element inthe LinkedDeque: 12
```

## 程序二

本程序涉及带有`String`元素的德格。

```java
// Java Program Demonstrate peekLast()
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

        // Displaying the last element
        System.out.println("Last Element in"
                   + "the LinkedDeque: " + cld.peekLast());
    }
}
```

**Output:**

```java
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg, GFG]
Last Element inthe LinkedDeque: GFG
```

## 参考

[`https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#peekLast--`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#peekLast--)