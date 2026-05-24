# Java 中的 `LinkedBlockingDeque.removeLast()` 方法

> 原文：[`https://www.geeksforgeeks.org/linkedblockingdeque-removelast-method-in-java/`](https://www.geeksforgeeks.org/linkedblockingdeque-removelast-method-in-java/)

`LinkedBlockingDeque` 的 `removeLast()` 方法返回并移除双端队列容器尾部的元素。如果双端队列是空的，该方法抛出一个 `NoSuchElementException`。

## 语法

```java
public E removeLast()
```

## 参数
该方法不接受任何参数。

## 返回
这个方法返回双端队列容器的尾部。

## 异常
如果双端队列为空，该函数抛出 `NoSuchElementException`。

下面的程序说明了 `LinkedBlockingDeque` 的 `removeLast()` 方法：

## 程序 1

```java
// Java Program to demonstrate removeLast()
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

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // removes the last element and prints it
        System.out.println("Linked Blocking Deque: " +
                        LBD.removeLast());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

## 输出

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque: 74381793
Linked Blocking Deque: [7855642, 35658786, 5278367]
```

## 程序 2

```java
// Java Program to demonstrate removeLast()
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

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // Deque is empty
        LBD.clear();

        // throws an exception
        LBD.removeLast();
    }
}
```

## 输出

```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeLast(LinkedBlockingDeque.java:462)
    at GFG.main(GFG.java:29)
```

## 参考
[`https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeLast--`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeLast--)