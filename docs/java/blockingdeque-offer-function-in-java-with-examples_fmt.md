# Java 中的 BlockingDeque offer() 函数示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-offer-function-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-offer-function-in-java-with-examples/)

`offer(E e)` 方法用于将参数中传递的元素插入到 `BlockingDeque` 的末尾。如果容器的容量已满，它不会像 `add()` 和 `addFirst()` 方法那样抛出异常。

## 语法

```java
public boolean offer(E e)
```

## 参数

该方法接受一个强制参数 `e`，它是要插入到 `BlockingDeque` 末尾的元素。

## 返回值

这个方法返回 `true` 如果元素已经插入，否则返回 `false`。

## 注意

`BlockingDeque` 的 `offer()` 方法继承自 Java 中的 [`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/) 类。

下面的程序说明了 `BlockingDeque` 的 `offer()` 方法：

### 程序 1

```java
// Java Program Demonstrate offer()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>(4);

        // Add numbers to end of BlockingDeque
        BD.offer(7855642);
        BD.offer(35658786);
        BD.offer(5278367);
        BD.offer(74381793);

        // Cannot be inserted
        BD.offer(10);

        // cannot be inserted hence returns false
        if (!BD.offer(10))
            System.out.println("The element 10 cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出**

```java
The element 10 cannot be inserted as capacity is full
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
```

### 程序 2

```java
// Java Program Demonstrate offer()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>(4);

        // Add numbers to end of BlockingDeque
        BD.offer("abc");
        BD.offer("gopu");
        BD.offer("geeks");
        BD.offer("richik");

        // Cannot be inserted
        BD.offer("hii");

        // cannot be inserted hence returns false
        if (!BD.offer("hii"))
            System.out.println("The element 'hii' cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + BD);
    }
}
```

**输出**

```java
The element 'hii' cannot be inserted as capacity is full
Blocking Deque: [abc, gopu, geeks, richik]
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offer(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offer(E))