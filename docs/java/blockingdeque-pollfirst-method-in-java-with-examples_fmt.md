# Java中BlockingDeque pollFirst()方法，带示例

> 原文：[https://www.geeksforgeeks.org/blockingdeque-pollfirst-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-pollfirst-method-in-java-with-examples/)

`BlockingDeque`的`pollFirst()`方法返回Deque容器中的前元素，并将其删除。如果容器是空的，它将返回`null`。

## 语法
```java
public E pollFirst()
```

## 参数
此方法不接受任何参数。

## 返回
如果容器不是空的，这个方法返回前元素在Deque容器中，并删除该元素。如果容器是空的，它将返回`null`。

## 注
`BlockingDeque`的`pollFirst()`方法继承自Java中的[`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了`pollFirst()`阻塞请求的方法：

### 程序1
```java
// Java Program Demonstrate pollFirst()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of BlockingDeque
        BlockingDeque<Integer> BD = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);
        BD.addFirst(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        // prints and deletes
        System.out.println("Front element in Deque: " + BD.pollFirst());

        // Deque after deletion of front element
        System.out.println("Blocking Deque: " + BD);
    }
}
```

### 输出
```java
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793
Blocking Deque: [5278367, 35658786, 7855642]
```

### 程序2
```java
// Java Program Demonstrate pollFirst()
// method of BlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args) {
        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> BD = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        // empty deque
        BD.clear();

        System.out.println("Front element in Deque: " + BD.pollFirst());
    }
}
```

### 输出
```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null
```

## 参考
[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#pollFirst(long, %20java.util.concurrent.TimeUnit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#pollFirst(long, %20java.util.concurrent.TimeUnit))