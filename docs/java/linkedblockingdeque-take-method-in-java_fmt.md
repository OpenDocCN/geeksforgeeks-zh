# Java 中 LinkedBlockingDeque take()方法

> 原文: [https://www.geeksforgeeks.org/linkedblockingdeque-take-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-take-method-in-java/)

`LinkedBlockingDeque` 的 `take()` 方法返回并从中移除双端队列的头部。如果在等待时被中断，该方法将抛出 `InterruptedException`。

## 语法
```java
public E take()
```

## 返回值
该方法返回双端队列的头部。

## 异常
如果在等待时被中断，该方法会抛出 `InterruptedException`。

下面的程序说明了 `LinkedBlockingDeque` 的 `take()` 方法：

## 程序 1
```java
// Java Program to demonstrate take()
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

        // removes the front element and prints it
        System.out.println("Head of Linked Blocking Deque: "
                           + LBD.take());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**
```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Linked Blocking Deque: 7855642
Linked Blocking Deque: [35658786, 5278367, 74381793]
```

## 程序 2：演示中断异常
```java
// Java Program to demonstrate take()
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

        // print Dequeue
        // the Deque is empty
        System.out.println("Linked Blocking Deque: " + LBD);

        try {
            // throws error as the list is empty
            // and it is interrupted while waiting
            System.out.println("Head of Linked Blocking Deque: "
                               + LBD.take());
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**
```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function.
```

## 参考
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#take--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#take--)