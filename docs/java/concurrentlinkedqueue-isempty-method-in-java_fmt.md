# Java 中的 ConcurrentLinkedQueue isEmpty()方法

> 原文：[https://www.geeksforgeeks.org/concurrentlinkedqueue-isempty-method-in-java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-isempty-method-in-java/)

`ConcurrentLinkedQueue`的`isEmpty()`方法用于检查该队列是否为空。如果`ConcurrentLinkedQueue`包含零个元素，则返回`true`，表示`ConcurrentLinkedQueue`为空。

## 语法

```java
public boolean isEmpty()
```

## 返回值

如果这个`ConcurrentLinkedQueue`包含零个元素，这个方法返回`true`。

## 示例

下面的程序说明了`ConcurrentLinkedQueue`的`isEmpty()`方法：

### 例 1

```java
// Java Program Demonstrate isEmpty()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");
        queue.add("Sanjeet");
        queue.add("Rabi");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // check whether queue isEmpty or not
        boolean response1 = queue.isEmpty();

        // print after applying isEmpty method
        System.out.println("Is Queue empty: " + response1);
    }
}
```

**输出：**

```java
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]
Is Queue empty: false
```

### 例 2

```java
// Java Program Demonstrate isEmpty()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // check whether queue is Empty
        boolean response1 = queue.isEmpty();

        // print after applying isEmpty method
        System.out.println("Is queue empty  : " + response1);
    }
}
```

**输出：**

```java
ConcurrentLinkedQueue: []
Is queue empty  : true
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#isEmpty--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#isEmpty--)