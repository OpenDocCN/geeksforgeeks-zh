# Java中的ConcurrentLinkedDeque.clear()方法

> 原文：[`https://www.geeksforgeeks.org/concurrentlinkeddeque-clear-method-in-java/`](https://www.geeksforgeeks.org/concurrentlinkeddeque-clear-method-in-java/)

## clear()方法
`clear()`方法是Java中的一个内置方法，它移除了Deque中的元素。

## 语法
```java
public void clear()
```

## 参数
该方法不接受任何参数。

## 返回值
函数不返回任何内容。

下面的程序举例说明了`ConcurrentLinkedDeque.clear()`方法：

### 程序1
```java
// Java Program to Demonstrate clear()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Remove all elements of the Deque using clear()
        cld.clear();

        // Displaying message
        System.out.println("\nConcurrentLinkedDeque cleared\n");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);
    }
}
```

## 输出
```java
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]

ConcurrentLinkedDeque cleared

ConcurrentLinkedDeque: []
```

### 程序2
```java
// Java Program to Demonstrate clear()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<Integer> cld
            = new ConcurrentLinkedDeque<Integer>();

        // Add elements into the Deque
        cld.add(10);
        cld.add(20);
        cld.add(30);
        cld.add(40);
        cld.add(50);

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Remove all elements of the Deque using clear()
        cld.clear();

        // Displaying message
        System.out.println("\nConcurrentLinkedDeque cleared\n");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);
    }
}
```

## 输出
```java
ConcurrentLinkedDeque: [10, 20, 30, 40, 50]

ConcurrentLinkedDeque cleared

ConcurrentLinkedDeque: []
```

## 参考
[`https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#clear--`](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#clear--)