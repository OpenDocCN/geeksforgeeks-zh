# Java 中 LinkedBlockingDeque takeFirst()方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-takefirst-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-takefirst-method-in-java/)

`takeFirst()` 方法将返回并从其中移除双端队列容器的第一个元素，如有必要，等待直到某个元素可用。如果在等待时被中断，该方法将抛出 `InterruptedException`。

## 语法

```java
public E takeFirst()
```

## 返回值

该方法返回双端队列容器的第一个元素，如有必要，等待直到某个元素可用。

## 异常

如果在等待时被中断，该方法会抛出 `InterruptedException`。

下面的程序说明了 `LinkedBlockingDeque` 的 `takeFirst()` 方法：

### 程序 1

```java
// Java Program to demonstrate takeFirst()
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
                           + LBD.takeFirst());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

### 输出

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Linked Blocking Deque: 7855642
Linked Blocking Deque: [35658786, 5278367, 74381793]
```

### 程序 2：演示中断异常

```java
// Java Program to demonstrate takeFirst()
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

        LBD.clear();

        // throws error as the list is empty and it
        // is interrupted while waiting
        System.out.println("Head of Linked Blocking Deque: "
                           + LBD.takeFirst());
    }
}
```

### 运行时错误

```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#takeFirst--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#takeFirst--)