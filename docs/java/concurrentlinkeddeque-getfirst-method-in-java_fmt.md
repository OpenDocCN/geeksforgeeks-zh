# Java 中的 ConcurrentLinkedDeque.getFirst() 方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-getfirst-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-getfirst-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.getFirst()` 方法是 Java 中的内置方法，它返回 deque 容器的第一个元素。

## 语法

```java
ConcurrentLinkedDeque.getFirst()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回 deque 中存在的第一个元素。

## 异常

当 deque 为空时，函数抛出 [`NoSuchElementException`](https://docs.oracle.com/javase/8/docs/api/java/util/NoSuchElementException.html)。

下面的程序说明了 `ConcurrentLinkedDeque.getFirst()` 方法：

### 程序 1

```java
/* Java Program to Demonstrate getFirst()
   method of ConcurrentLinkedDeque */

import java.util.concurrent.*;
class GFG {
    public static void main(String[] args)
    {

// Creating an empty Deque
        ConcurrentLinkedDeque<String> cld = 
                    new ConcurrentLinkedDeque<String>();

// Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

// Displaying the Deque
        System.out.println("Elements in the Deque: " + cld);

// Displaying the first element
        System.out.println("The first element is: " +
                                     cld.getFirst());
    }
}
```

**输出：**

```java
Elements in the Deque: [Welcome, To, Geeks, 4, Geeks]
The first element is: Welcome
```

### 程序 2

```java
/* Java Program to Demonstrate getFirst()
   method of ConcurrentLinkedDeque */

import java.util.concurrent.*;
class GFG {
    public static void main(String[] args)
    {

// Creating an empty Deque
        ConcurrentLinkedDeque<Integer> cld = 
                         new ConcurrentLinkedDeque<Integer>();

try {
            // Displaying the first element
            System.out.println("The first element "
                         + "is: " + cld.getFirst());
        }
        catch (Exception e) {
            System.out.println(e);
        }

// Add elements into the Deque
        cld.add(12);
        cld.add(43);
        cld.add(29);
        cld.add(16);
        cld.add(70);

// Displaying the Deque
        System.out.println("Elements in the Deque: " + cld);

// Displaying the first element
        System.out.println("The first element is: " +
                                   cld.getFirst());
    }
}
```

**输出：**

```java
java.util.NoSuchElementException
Elements in the Deque: [12, 43, 29, 16, 70]
The first element is: 12
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#getFirst--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#getFirst--)