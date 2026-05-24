# Java 中 BlockingDeque poll()方法，带示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-poll-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-poll-method-in-java-with-examples/)

`BlockingDeque`的`poll()`方法返回 Deque 容器中的前元素并删除它。如果容器是空的，它将返回`null`。

## 语法

```java
public E poll()
```

## 参数

此方法不接受任何参数。

## 返回值

如果容器不是空的，这个方法返回*Deque 容器的前元素*并删除它。如果容器是空的，它将返回*空值*。

## 注

`BlockingDeque`的`poll()`方法继承自 Java 中的[`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了`BlockingDeque`的`poll()`方法：

### 程序 1

```java
// Java Program Demonstrate poll()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        System.out.println("Front element in Deque: " + BD.poll());

        // One element is deleted as poll was called
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出：**

```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: 7855642
Blocking Deque: [35658786, 5278367, 74381793]
```

### 程序 2

```java
// Java Program Demonstrate poll()
// method of BlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        // empty deque
        BD.clear();

        System.out.println("Front element in Deque: " + BD.poll());
    }
}
```

**输出：**

```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#poll(long, %20java.util.concurrent.TimeUnit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#poll(long, %20java.util.concurrent.TimeUnit))