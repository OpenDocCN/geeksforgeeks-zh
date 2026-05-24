# Java 中的 BlockingDeque removeLastOccurrence() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-removelastoccurrence-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-removelastoccurrence-method-in-java-with-examples/)

## 方法描述

`removeLastOccurrence()` 方法从 `BlockingDeque` 中移除指定元素的最后一次出现。如果 deque 不包含该元素，它将保持不变。如果这个 deque 包含指定的元素，则返回 `true`，否则返回 `false`。

### 语法

```java
public boolean removeLastOccurrence(Object o)
```

### 参数

该方法接受一个强制参数 `o`，该参数指定最后一次出现的元素将从 deque 容器中移除。

### 返回值

该方法返回 `true` 如果元素存在并从 deque 容器中移除，否则返回 `false`。

### 注意

`BlockingDeque` 的 `removeLastOccurrence()` 方法继承自 Java 中的 `LinkedBlockingDeque` 类。

## 示例程序

下面的程序说明了 `BlockingDeque` 的 `removeLastOccurrence()` 方法：

### 程序 1：当元素存在时

```java
// Java Program to demonstrate removeLastOccurrence()
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
        BD.add(15);
        BD.add(20);
        BD.add(20);
        BD.add(15);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);

        if (BD.removeLastOccurrence(15))
            System.out.println("Last occurrence of 15 removed");
        else
            System.out.println("15 not present and not removed");

        // prints the Deque after removal
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出：**

```
Blocking Deque: [15, 20, 20, 15]
Last occurrence of 15 removed
Blocking Deque: [15, 20, 20]
```

### 程序 2：当元素不存在时

```java
// Java Program to demonstrate removeLastOccurrence()
// method of BlockingDeque

import java.util.concurrent.BlockingDeque;
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(15);
        BD.add(20);
        BD.add(20);
        BD.add(15);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        if (BD.removeLastOccurrence(10))
            System.out.println("Last occurrence of 10 removed");
        else
            System.out.println("10 not present and not removed");

        // prints the Deque after removal
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出：**

```
Blocking Deque: [15, 20, 20, 15]
10 not present and not removed
Blocking Deque: [15, 20, 20, 15]
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#removeLastOccurrence(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#removeLastOccurrence(java.lang.Object))