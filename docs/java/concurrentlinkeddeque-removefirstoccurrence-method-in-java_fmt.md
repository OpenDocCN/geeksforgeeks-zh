# Java 中的 ConcurrentLinkedDeque removeFirstOccurrence() 方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-removefirstoccurrence-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-removefirstoccurrence-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.removeFirstOccurrence()` 方法是 Java 中的一个内置方法，它接受一个参数，并删除该元素在 deque 中的第一次出现。因此，在元素不存在于 deque 中的情况下，它保持不变。

## 语法

```java
public boolean removeFirstOccurrence(Object o)
```

## 参数

该函数接受一个对象 `o` 作为参数，该参数表示其在 deque 中的第一次出现将被删除的对象。

## 返回值

如果 deque 中存在 `o`，则函数返回 `true`，否则返回 `false`。

## 异常

如果作为参数传递给函数的指定元素为空，函数将抛出 `NullPointerException`。

## 示例

以下程序说明了 `removeFirstOccurrence()` 方法的使用：

### 程序 1

```java
/* Java program to demonstrate 
   removeFirstOccurrence() method
   of ConcurrentLinkedDeque   */

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Geeks");
        cld.addFirst("Gfg");
        cld.addFirst("gfg");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);

        // Remove first occurrence of  element
        cld.removeFirstOccurrence("Geeks");

        // Displaying the modified LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出：**

```java
Elements in the LinkedDeque: [Geeks, gfg, Gfg, Geeks, GFG]
Elements in the LinkedDeque: [gfg, Gfg, Geeks, GFG]
```

### 程序 2

```java
/* Java program to demonstrate 
   removeFirstOccurrence() method
   of ConcurrentLinkedDeque   */

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld = new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(280);
        cld.addFirst(1008);
        cld.addFirst(1050);
        cld.addFirst(379);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);
        try {
            // Remove first occurrence of  element
            cld.removeFirstOccurrence(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
Elements in the LinkedDeque: [379, 1050, 1008, 280, 12]
java.lang.NullPointerException
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#removeFirstOccurrence-java.lang.Object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#removeFirstOccurrence-java.lang.Object-)