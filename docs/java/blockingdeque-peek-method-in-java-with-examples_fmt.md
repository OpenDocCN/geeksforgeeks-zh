# Java 中的 BlockingDeque peek()方法，带示例

> 原文: [https://www.geeksforgeeks.org/blockingdeque-peek-method-in-java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-peek-method-in-java-with-examples/)

`BlockingDeque`的`peek()`方法返回双端容器中的前元素。如果容器是空的，它将返回`null`。

## 语法

```java
public E peek()
```

## 参数

此方法不接受任何参数。

## 返回

如果容器不是空的，该方法返回双端容器中的前元素。如果容器为空，则返回`null`。

**注**：`BlockingDeque`的`peek()`方法继承自 Java 中的[`LinkedBlockingDeque`](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了`peek()`方法的`BlockingDeque`:

## 程序 1

```java
// Java Program Demonstrate peek()
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
        System.out.println("Linked Blocking Deque: " + BD);

System.out.println("Front element in Deque: " + BD.peek());
    }
}
```

## 输出

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: 7855642
```

## 程序 2

```java
// Java Program Demonstrate peek()
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

System.out.println("Front element in Deque: " + BD.peek());
    }
}
```

## 输出

```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#peek()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#peek())