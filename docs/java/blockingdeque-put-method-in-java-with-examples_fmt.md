# Java 中的 BlockingDeque put()方法，示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-put-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-put-method-in-java-with-examples/)

`BlockingDeque`的`put(E e)`方法将指定的元素插入到这个双端队列所代表的队列中（换句话说，在这个双端队列的尾部）。如果双端队列是容量受限的，那么它将等待空间变得可用。

## 语法：
```java
public void put(E e)
```

## 参数：
该方法接受一个强制参数`e`，它是要插入到`BlockingDeque`末尾的元素。

## 返回：
此方法不返回任何内容。

## 异常：
程序抛出如下所示的两个异常：
*   `NullPointerException` - 如果指定的元素为空。
*   `InterruptedException` – 如果在等待时被中断。

## 注：
`BlockingDeque`的`put()`方法继承了 Java 中的`LinkedBlockingDeque`类。

下面的程序说明了`put()`方法的`BlockingDeque`：

### 程序 1：
```java
// Java Program Demonstrate put()
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
        BD.put(7855642);
        BD.put(35658786);
        BD.put(5278367);
        BD.put(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出：**
```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
```

### 节目 2：
```java
// Java Program Demonstrate put()
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
        BD.put(7855642);
        BD.put(35658786);
        BD.put(5278367);

        // throws an exception
        BD.put(null);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出：**
```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putLast(LinkedBlockingDeque.java:390)
    at java.util.concurrent.LinkedBlockingDeque.put(LinkedBlockingDeque.java:649)
    at GFG.main(GFG.java:24)
```

### 节目 3：
```java
// Java Program Demonstrate put()
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
        BD.put(7855642);
        BD.put(35658786);
        BD.put(5278367);

        // throws an exception
        BD.put(4356789);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```
**输出：**
```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#put(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#put(E))