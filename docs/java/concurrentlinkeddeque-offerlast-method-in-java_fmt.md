# Java 中的 `ConcurrentLinkedDeque.offerLast()` 方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-offerlast-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-offerlast-method-in-java/)

`java.util.concurrent.ConcurrentLinkedDeque.offerLast()` 方法是 Java 中的一个内置方法，它将作为参数传递的指定元素插入到 deque 的末尾。

## 语法

```java
Conn_Linked_Deque.offerLast(Object elem)
```

## 参数

该方法接受一个参数 `elem`，该参数指定了要插入到数据末尾的元素。

## 返回值

如果元素成功添加到德格中，函数返回 `true`，否则返回 `false`。

## 异常

如果传递的参数为 `null`，则函数抛出 `NullPointerException`。

下面的程序说明了 `ConcurrentLinkedDeque.offerLast()` 方法：

### 程序 1

```java
/* Java Program to Demonstrate offerLast()
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
        System.out.println("Elements in Deque: "
                           + cld);

// Displaying the Last element
        System.out.println("The Last element is: " + 
                                      cld.getLast());

/* Insert an element at the tail
            of the deque */
        if (cld.offerLast("GFG")) {
            // Displaying the Last element
            System.out.println("The Inserted element is: " + 
                                      cld.getLast());
        }

// Displaying the Deque
        System.out.println("Elements in Deque: "
                           + cld);

// Displaying the Last element
        System.out.println("The Last element is: " + 
                                      cld.getLast());
    }
}
```

### 输出

```java
Elements in Deque: [Welcome, To, Geeks, 4, Geeks]
The Last element is: Geeks
The Inserted element is: GFG
Elements in Deque: [Welcome, To, Geeks, 4, Geeks, GFG]
The Last element is: GFG
```

### 程序 2

```java
/* Java Program to Demonstrate offerLast()
   method of ConcurrentLinkedDeque */

import java.util.concurrent.*;
class GFG {
    public static void main(String[] args)
    {

// Creating an empty Deque
        ConcurrentLinkedDeque<Integer> cld = 
                  new ConcurrentLinkedDeque<Integer>();

// Add elements into the Deque
        cld.add(12);
        cld.add(43);
        cld.add(29);
        cld.add(16);
        cld.add(70);

// Displaying the Deque
        System.out.println("Elements in Deque: "
                           + cld);

// Displaying the Last element
        System.out.println("The Last element is: " + 
                                      cld.getLast());

try {
            cld.offerLast(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }

/* Insert an element at the tail
            of the deque */
        if (cld.offerLast(24)) {
            // Displaying the Last element
            System.out.println("The Inserted element is: "
                                  + cld.getLast());
        }

// Displaying the Deque
        System.out.println("Elements in Deque: "
                           + cld);

// Displaying the Last element
        System.out.println("The Last element is: " +
                                       cld.getLast());
    }
}
```

### 输出

```java
Elements in Deque: [12, 43, 29, 16, 70]
The Last element is: 70
java.lang.NullPointerException
The Inserted element is: 24
Elements in Deque: [12, 43, 29, 16, 70, 24]
The Last element is: 24
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#offerLast-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#offerLast-E-)