# Java中`BlockingDeque`的`offerFirst()`方法，带示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-offerfirst-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-offerfirst-method-in-java-with-examples/)

`offerFirst(E e)`方法将参数中传递的元素插入到`Deque`容器的前面。如果容器的容量已经超出，那么它不会像`add()`和`addFirst()`函数那样返回异常。

## 语法
```java
public boolean offerFirst(E e)
```

## 参数
该方法接受一个强制参数`e`，它是要插入到阻塞请求前面的元素。

## 返回
这个方法返回`true`如果元素已经插入，否则返回`false`。

## 注
`BlockingDeque`的`offerFirst()`方法继承自Java中的[`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了`LinkedBlockingDeque`的`offerFirst()`方法：

## 程序1

```java
// Java Program Demonstrate offerFirst()
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
        BD.offerFirst(7855642);
        BD.offerFirst(35658786);
        BD.offerFirst(5278367);
        BD.offerFirst(74381793);

        // Cannot be inserted
        BD.offerFirst(10);

        // cannot be inserted hence returns false
        if (!BD.offerFirst(10))
            System.out.println("The element 10 cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:**
```java
The element 10 cannot be inserted as capacity is full
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
```

## 程序2

```java
// Java Program Demonstrate offerFirst()
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
        BD.offerFirst("abc");
        BD.offerFirst("gopu");
        BD.offerFirst("geeks");
        BD.offerFirst("richik");

        // Cannot be inserted
        BD.offerFirst("hii");

        // cannot be inserted hence returns false
        if (!BD.offerFirst("hii"))
            System.out.println("The element 'hii' cannot be"
                               + " inserted as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:**
```java
The element 'hii' cannot be inserted as capacity is full
Blocking Deque: [richik, geeks, gopu, abc]
```

**参考：**[`https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offerFirst(E)`](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offerFirst(E))