# Java 中的 ConcurrentLinkedDeque poll() 方法示例

> 原文：[https://www.geeksforgeeks.org/concurrentlinkeddeque-poll-method-in-java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-poll-method-in-java-with-example/)

`ConcurrentLinkedDeque` 的 `poll()` 方法返回双端队列（Deque）中的前端元素并删除它。如果容器是空的，它将返回 `null`。

## 语法

```java
public E poll()
```

## 参数

此方法不接受任何参数。

## 返回值

如果容器不是空的，这个方法返回 `前元素` 并删除它。如果容器是空的，它将返回 `null`。

以下程序说明了 `ConcurrentLinkedDeque` 的 `poll()` 方法：

## 程序 1

```java
// Java Program Demonstrate poll()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

{

// create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

// Add numbers to end of ConcurrentLinkedDeque
        CLD.add(7855642);
        CLD.add(35658786);
        CLD.add(5278367);
        CLD.add(74381793);

// Print the queue
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);

System.out.println("Front element in Deque: "
                           + CLD.poll());

// One element is deleted as poll was called
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);
    }
}
```

**Output:**

```java
ConcurrentLinkedDeque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: 7855642
ConcurrentLinkedDeque: [35658786, 5278367, 74381793]
```

## 程序 2

```java
// Java Program Demonstrate poll()
// method of ConcurrentLinkedDeque
// when Deque is empty

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

{

// create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

// Add numbers to end of ConcurrentLinkedDeque
        CLD.add(7855642);
        CLD.add(35658786);
        CLD.add(5278367);
        CLD.add(74381793);

// Print the queue
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);

// empty deque
        CLD.clear();

System.out.println("Front element in Deque: "
                           + CLD.poll());
    }
}
```

**Output:**

```java
ConcurrentLinkedDeque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null
```