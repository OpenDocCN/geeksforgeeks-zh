# BlockingQueue 中的 contains() 方法（Java 示例）

> 原文：[https://www.geeksforgeeks.org/blockingqueue-contains-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-contains-method-in-java-with-examples/)

`contains(Object o)` 方法属于 `BlockingQueue` 接口，用于检查容器中是否存在参数传递的元素。如果元素存在于容器中，则返回 `true`，否则返回 `false`。

## 语法

```java
public boolean contains(Object o)
```

## 参数

该方法接受一个强制参数 `o`，其在容器中的存在性将被检查。

## 返回值

如果元素存在，此方法返回 `true`，否则返回 `false`。

## 继承关系

`contains()` 方法继承自 Java 中的 `Queue` 类。

## 程序 1

以下程序演示了 `BlockingQueue` 的 `contains()` 方法：

```java
// Java Program Demonstrate contains()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingQueue
        BlockingQueue<Integer> BQ
            = new LinkedBlockingQueue<Integer>();

        // Add numbers to end of BlockingQueue
        BQ.add(10);
        BQ.add(20);
        BQ.add(30);
        BQ.add(40);

        // before removing print queue
        System.out.println("Blocking Queue: " + BQ);

        // check for presence using function
        if (BQ.contains(10)) {
            System.out.println("Blocking Queue contains 10");
        }
        else {
            System.out.println("Blocking Queue does not contain 10");
        }
    }
}
```

### 输出

```java
Blocking Queue: [10, 20, 30, 40]
Blocking Queue contains 10
```

## 程序 2

```java
// Java Program Demonstrate contains()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>();

        // Add numbers to end of BlockingQueue
        BQ.add("ab");
        BQ.add("cd");
        BQ.add("fg");
        BQ.add("xz");

        // before removing print queue
        System.out.println("Blocking Queue: " + BQ);

        // check for presence using function
        if (BQ.contains("go")) {
            System.out.println("Blocking Queue contains 'go'");
        }
        else {
            System.out.println("Blocking Queue does not contain 'go'");
        }
    }
}
```

### 输出

```java
Blocking Queue: [ab, cd, fg, xz]
Blocking Queue does not contain 'go'
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingQueue.html#contains(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingQueue.html#contains(java.lang.Object))