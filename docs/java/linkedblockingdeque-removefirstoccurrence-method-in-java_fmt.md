# Java中的`LinkedBlockingDeque.removeFirstOccurrence()`方法

> 原文：[https://www.geeksforgeeks.org/linkedblockingdeque-removefirstoccurrence-method-in-java/](https://www.geeksforgeeks.org/linkedblockingdeque-removefirstoccurrence-method-in-java/)

`LinkedBlockingDeque`的`removeFirstOccurrence()`方法从此双端队列中移除指定元素的第一次出现。如果双端队列不包含该元素，它将保持不变。如果此双端队列包含指定的元素，则返回`true`，否则返回`false`。

## 语法

```java
public boolean removeFirstOccurrence(Object o)
```

## 参数

该方法接受一个强制参数`o`，该参数指定要从双端队列容器中移除的元素。

## 返回值

此方法返回`true`如果元素存在并从双端队列容器中移除，否则返回`false`。

下面的程序说明了当元素存在时`LinkedBlockingDeque`的`removeFirstOccurrence()`方法：

### 程序1：元素存在时

```java
// Java Program to demonstrate removeFirstOccurrence()
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
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        if (LBD.removeFirstOccurrence(15))
            System.out.println("First occurrence of 15 removed");
        else
            System.out.println("15 not present and not removed");

        // prints the Deque after removal
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出**

```java
Linked Blocking Deque: [15, 20, 20, 15]
First occurrence of 15 removed
Linked Blocking Deque: [20, 20, 15]
```

### 程序2：元素不存在时

```java
// Java Program to demonstrate removeFirstOccurrence()
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
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        if (LBD.removeFirstOccurrence(10))
            System.out.println("First occurrence of 10 removed");
        else
            System.out.println("10 not present and not removed");

        // prints the Deque after removal
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出：**

```java
Linked Blocking Deque: [15, 20, 20, 15]
10 not present and not removed
Linked Blocking Deque: [15, 20, 20, 15]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeFirstOccurrence-java.lang.Object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeFirstOccurrence-java.lang.Object-)