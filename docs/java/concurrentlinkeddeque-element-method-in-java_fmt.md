# Java 中的 ConcurrentLinkedDeque element() 方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-element-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-element-method-in-java/)

[`ConcurrentLinkedDeque`](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/) 的 `element()` 是 Java 中的内置函数，它检索但不移除由 deque 表示的队列头，即 deque 的第一个元素。

**语法：**

```java
conn_linked_deque.element()
```

**参数：** 该方法没有参数。
**返回值：** 此方法返回 deque 中的第一个元素。
**异常：** 如果 deque 为空，此方法会抛出 `NoSuchElementException`。

以下程序说明了 `ConcurrentLinkedDeque` 的 `element()` 方法：

**程序 1：** 该程序涉及一个整数类型的 `ConcurrentLinkedDeque`。

### Java 程序示例 1

```java
// Java example illustrating
// ConcurrentLinkedDeque element() method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        cld.add(12);
        cld.add(70);
        cld.add(1009);
        cld.add(475);

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Displaying the head of deque
        System.out.println("The Head of deque is: "
                           + cld.element());
    }
}
```

**输出：**

```java
ConcurrentLinkedDeque: [12, 70, 1009, 475]
The Head of deque is: 12
```

**程序 2：** 该程序涉及一个字符串类型的 `ConcurrentLinkedDeque`。

### Java 程序示例 2

```java
// Java example illustrating
// ConcurrentLinkedDeque element() method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<String>
            cld = new ConcurrentLinkedDeque<String>();

        cld.add("Gfg");
        cld.add("Geeks");
        cld.add("Programming");
        cld.add("contribute");

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Displaying the head of deque
        System.out.println("The Head of deque is: "
                           + cld.element());
    }
}
```

**输出：**

```java
ConcurrentLinkedDeque: [Gfg, Geeks, Programming, contribute]
The Head of deque is: Gfg
```