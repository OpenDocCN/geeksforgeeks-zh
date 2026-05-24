# Java 中的 BlockingDeque putFirst()方法，带示例

> 原文: [https://www.geeksforgeeks.org/blockingdeque-putfirst-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-putfirst-method-in-java-with-examples/)

`BlockingDeque`的`putFirst(E e)`方法将指定的元素插入到这个双端队列的前面。如果队列是容量受限的，那么它将等待空间变得可用。

## 语法:
```java
public void putFirst(E e)
```

## 参数:
该方法接受一个强制参数`e`，它是要插入到阻塞双端队列前面的元素。

## 返回:
此方法不返回任何内容。

## 异常:
程序抛出如下所示的两个异常:
*   `NullPointerException` - 如果指定的元素为空。
*   `InterruptedException` – 如果在等待时被中断。

## 注:
`BlockingDeque`的`putFirst()`方法继承自 Java 中的`LinkedBlockingDeque`类。

下面的程序说明了`BlockingDeque`的`putFirst()`方法:

### 程序 1:
```java
// Java Program Demonstrate putFirst()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);
        BD.putFirst(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出:**
```java
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
```

### 程序 2:
```java
// Java Program Demonstrate putFirst()
// method of BlockingDeque
// throwing NullPointerException

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);

        // throws an exception
        BD.putFirst(null);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出:**
```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putFirst(LinkedBlockingDeque.java:373)
    at GFG.main(GFG.java:24)
```

### 程序 3:
```java
// Java Program Demonstrate putFirst()
// method of BlockingDeque
// when capacity exceeded

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of BlockingDeque
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);

        // throws an exception
        BD.putFirst(4356789);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出:**
```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function
```

**参考:** [https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#putFirst(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#putFirst(E))