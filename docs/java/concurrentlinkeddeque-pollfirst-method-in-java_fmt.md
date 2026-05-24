# Java 中的 ConcurrentLinkedDeque.pollFirst() 方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-pollfirst-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-pollfirst-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.pollFirst()` 是 Java 中的一个内置方法，它检索这个 deque 的第一个元素并将其移除。如果此 deque 为空，则该方法返回 `null`。

## 语法

```java
Conn_Linked_Deque.pollFirst()
```

## 参数

该功能不接受任何参数。

## 返回值

函数返回此 deque 的第一个元素。如果此 deque 为空，则该功能返回 `null`。

下面的程序说明了 `pollFirst()` 方法的使用：

### 程序 1

该程序涉及带有 `Integer` 元素的 deque。

```java
// Java Program Demonstrate pollFirst() 
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld = 
                    new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(70);
        cld.addFirst(1009);
        cld.addFirst(475);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Display and remove the first element
        System.out.println("Element removed : "
                           + cld.pollFirst());

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出：**

```java
Elements inthe LinkedDeque: [475, 1009, 70, 12]
Element removed : 475
Elements inthe LinkedDeque: [1009, 70, 12]
```

### 程序 2

这个程序涉及到带有 `String` 元素的 deque。

```java
// Java Program Demonstrate pollFirst() 
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                        new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Geeks");
        cld.addFirst("Gfg");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Display and remove the First element
        System.out.println("Element removed : "
                           + cld.pollFirst());

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出：**

```java
Elements inthe LinkedDeque: [Geeks, Gfg, Geeks, GFG]
Element removed : Geeks
Elements inthe LinkedDeque: [Gfg, Geeks, GFG]
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#pollFirst--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#pollFirst--)