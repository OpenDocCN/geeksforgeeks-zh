# Java 中的 BlockingDeque remove()方法，示例

> 原文: [https://www.geeksforgeeks.org/blockingdeque-remove-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-remove-method-in-java-with-examples/)

`remove()`方法`阻塞`移出`Deque`容器的头部。如果`Deque`容器是空的，该方法抛出一个`NoSuchElementException`。如果参数中传入了一个元素，它将移除给定的元素(如果存在于`Deque`中)。

## 语法:
```java
public E remove() or boolean remove(element)
```

## 参数:
该方法接受一个临时参数`element`，该元素将从`BlockingDeque`中删除。

## 返回:
如果参数被传递，该方法返回真或假，否则不返回任何内容。如果元素在`Deque`中，则返回`true`，否则返回`false`。

## 异常:
如果`Deque`为空，该函数抛出`NoSuchElementException`。

## 注意:
`BlockingDeque`的`remove()`方法继承自`LinkedBlockingDeque`类。

下面的程序说明了`remove()`方法的`BlockingDeque`:

### 程序 1:
```java
// Java Program Demonstrate remove()
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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // removes the front element
        BD.remove();
        System.out.println("Blocking Deque: " + BD);

        // removes the element
        BD.remove(5278367);
        System.out.println("Blocking Deque: " + BD);
    }
}
```

### 输出:
```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Blocking Deque: [35658786, 5278367, 74381793]
Blocking Deque: [35658786, 74381793]
```

### 程序 2:
```java
// Java Program Demonstrate remove()
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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        BD.clear();

        // removes the front element
        BD.remove();
        System.out.println("Blocking Deque: " + BD);

        // removes the element
        BD.remove(5278367);
        System.out.println("Blocking Deque: " + BD);
    }
}
```

### 输出:
```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeFirst(LinkedBlockingDeque.java:453)
    at java.util.concurrent.LinkedBlockingDeque.remove(LinkedBlockingDeque.java:672)
    at GFG.main(GFG.java:29)
```

## 参考:
[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#remove()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#remove())