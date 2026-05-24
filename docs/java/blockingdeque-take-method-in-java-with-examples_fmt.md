# Java中`BlockingDeque` `take()`方法示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-take-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-take-method-in-java-with-examples/)

`BlockingDeque`的`take()`方法返回并移除 deque 容器的头部。如果在等待时被中断，该方法将抛出`InterruptedException`。

## 语法
```java
public E take()
```

## 返回
该方法返回 deque 容器的头部。

## 异常
如果在等待时被中断，该方法会抛出`InterruptedException`。

## 注
`BlockingDeque`的`take()`方法继承自 Java 中的`LinkedBlockingDeque`类。

下面程序举例说明`BlockingDeque`的`take()`方法：

### 程序 1
```java
// Java Program to demonstrate take()
// method of LinkedBlockingDeque

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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // removes the front element and prints it
        System.out.println("Head of Blocking Deque: "
                           + BD.take());

        // prints the Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出：**
```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Blocking Deque: 7855642
Blocking Deque: [35658786, 5278367, 74381793]
```

### 程序 2：演示中断异常
```java
// Java Program to demonstrate take()
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

        // print Dequeue
        // the Deque is empty
        System.out.println("Blocking Deque: " + BD);

        try {
            // throws error as the list is empty
            // and it is interrupted while waiting
            System.out.println("Head of Blocking Deque: "
                               + BD.take());
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**运行时错误：**
```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function.
```

**参考：**[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#take()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#take())