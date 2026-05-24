# Java 中的 ConcurrentLinkedDeque addFirst()方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-addfirst-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-addfirst-method-in-java/)

`java.util.ConcurrentLinkedDeque.addFirst()` 是 Java 中的内置函数，它在 `ConcurrentLinkedDeque` 的前面插入指定的元素。

## 语法

```java
conn_linked_deque.addFirst(elem)
```

## 参数

该方法只接受单个参数 `elem`，该参数将被添加到 `ConcurrentLinkedDeque` 的开头。

## 返回值

函数没有返回值。

## 异常

当传递给函数的参数为 `null` 时，该方法将抛出 [`NullPointerException`](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html)。由于其有界性，该方法永远不会抛出 `IllegalStateException` 或返回 `false`。

下面的程序说明了 `ConcurrentLinkedDeque.addFirst()` 方法：

### 程序 1

该程序涉及一个整数类型的 `ConcurrentLinkedDeque`。

```java
// Java Program Demonstrate addFirst()
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
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);

        // Insert a new element in the  LinkedDeque
        cld.addFirst(21);

        // Displaying the modified LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出：**

```java
Initial Elements inthe LinkedDeque: [76, 55, 110, 12]
Initial Elements inthe LinkedDeque: [21, 76, 55, 110, 12]
```

### 程序 2

当 `null` 作为参数传递给函数时，该程序涉及带有异常处理的整数类型的 `ConcurrentLinkedDeque`。

```java
// Java Program Demonstrate addFirst()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                         new ConcurrentLinkedDeque<String>();

        cld.addFirst("Geeks");
        cld.addFirst("Geek");
        cld.addFirst("Gfg");
        cld.addFirst("Contribute");

        // Displaying the existing LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);

        /* Exception thrown when null 
             is passed as parameter*/
        try {
            cld.addFirst(null);
        }
        catch (NullPointerException e) {
            System.out.println("NullPointerException"
                               + "thrown");
        }

        // Insert a new element in the  LinkedDeque
        cld.addFirst("Sudo Placement");

        // Displaying the modified LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出：**

```java
Initial Elements inthe LinkedDeque: [Contribute, Gfg, Geek, Geeks]
NullPointerExceptionthrown
Initial Elements inthe LinkedDeque: [Sudo Placement, Contribute, Gfg, Geek, Geeks]
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#addFirst(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#addFirst(java.lang.Object))