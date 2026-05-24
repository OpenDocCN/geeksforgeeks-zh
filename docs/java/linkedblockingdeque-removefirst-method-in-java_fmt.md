# Java 中的 `LinkedBlockingDeque.removeFirst()` 方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-removefirst-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-removefirst-method-in-java/)

`LinkedBlockingDeque` 的 `removeFirst()` 方法返回并从双端队列容器中移除第一个元素。如果双端队列容器是空的，该方法抛出一个 `NoSuchElementException`。

## 语法

```java
public E removeFirst()
```

## 返回值

该方法返回双端队列的头，这是第一个元素。

## 异常

如果双端队列为空，该函数抛出 `NoSuchElementException`。

下面的程序说明了 `LinkedBlockingDeque` 的 `removeFirst()` 方法：

## 程序 1

```java
// Java Program to demonstrate removeFirst()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Deque
        System.out.println("Linked Blocking Deque: " + LBD);

        // removes the front element and prints it
        System.out.println("First element of Linked Blocking Deque: "
                           + LBD.removeFirst());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

## 输出

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]

First element of Linked Blocking Deque: 7855642

Linked Blocking Deque: [35658786, 5278367, 74381793]
```

## 程序 2

```java
// Java Program to demonstrate removeFirst()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws NoSuchElementException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // print Deque
        System.out.println("Linked Blocking Deque: " + LBD);

        try {
            // throws an exception
            LBD.removeFirst();
        }
        catch (Exception e) {
            System.out.println("Exception when removing "
                               + "first element from this Deque: "
                               + e);
        }
    }
}
```

## 输出

```java
Linked Blocking Deque: []
Exception when removing first element from this Deque: java.util.NoSuchElementException
```