# Java 中 LinkedBlockingDeque putFirst()方法

> 原文: [https://www.geeksforgeeks.org/linkedblockingdeque-putfirst-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-putfirst-method-in-java/)

`putFirst(E e)` 方法在 `LinkedBlockingDeque` 中将指定的元素插入到这个队列所代表的队列的前面。如果 deque 是容量受限的，那么它将等待空间变得可用。

## 语法

```java
public void putFirst(E e)
```

## 参数

该方法接受一个强制参数 `e`，它是要插入到 `LinkedBlockingDeque` 前面的元素。

## 返回

此方法不返回任何内容。

## 异常

程序抛出如下所示的两个异常:

*   `NullPointerException` - 如果指定的元素为空。
*   `InterruptedException` – 如果在等待时被中断。

下面的程序说明了 `LinkedBlockingDeque` 的 `putFirst()` 方法:

## 程序 1

```java
// Java Program Demonstrate putFirst()
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
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);
        LBD.putFirst(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
```

## 程序 2

```java
// Java Program Demonstrate putFirst()
// method of LinkedBlockingDeque
// throwing NullPointerException

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
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);

        // throws an exception
        LBD.putFirst(null);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putFirst(LinkedBlockingDeque.java:373)
    at GFG.main(GFG.java:23)
```

## 程序 3

```java
// Java Program Demonstrate putFirst()
// method of LinkedBlockingDeque
// when capacity exceeded

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of LinkedBlockingDeque
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);

        // throws an exception
        LBD.putFirst(4356789);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Runtime Errors:
Max real time limit exceeded due to either by
heavy load on server or by using sleep function
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#putFirst-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#putFirst-E-)