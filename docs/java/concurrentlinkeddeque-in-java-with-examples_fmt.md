# Java 中的 ConcurrentLinkedDeque 附带示例

> 原文: [https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/)

Java 中的 `ConcurrentLinkedDeque` 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分，实现了 `Deque` 接口和 `AbstractCollection` 类。属于 `java.util.concurrent` 包。用于同时借助[链接表](https://www.geeksforgeeks.org/linked-list-set-1-introduction/)实现[双端队列](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/)。

## 并发链接请求的特征

*   迭代器和分割器弱一致。
*   并发的插入、移除和访问操作跨多个线程安全地执行。
*   它不允许空元素。
*   `size()` 方法不是在恒定时间内实现的。由于这些元素的异步特性，确定当前的元素数量需要遍历这些元素。

## 类层次结构:

![ConcurrentLinkedDeque in Java](img/ecb88e0d744da18bef99277f6425cfb2.png)

## 声明:

```java
public abstract class ConcurrentLinkedDeque<E>
   extends AbstractCollection<E>
      implements Deque<E>, Serializable
```

Here, `E` is the type of elements maintained by this collection.

它实现了 `Serializable`、`Iterable<E>`、`Collection<E>`、`Deque<E>`、`Queue<E>` 接口。

### ConcurrentLinkedDeque 的构造函数:

**1. `ConcurrentLinkedDeque()`**: 这个构造函数是用来构造一个空的 deque。

```java
ConcurrentLinkedDeque<E> cld = new ConcurrentLinkedDeque<E>();
```

**2. `ConcurrentLinkedDeque(Collection<? extends E> c)`**: 这个构造函数用来构造一个 deque，集合的元素作为参数传递。

```java
ConcurrentLinkedDeque<E> cld = new ConcurrentLinkedDeque<E>(c);
```

下面是用 Java 说明 ConcurrentLinkedDeque 的示例程序:

## 示例代码

```java
// Java Program to demonstrate ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {

    public static void main(String[] args)
    {
        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() 
        // constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        // add element to the front
        // using addFirst() method
        cld.addFirst(12);
        cld.addFirst(70);
        cld.addFirst(1009);
        cld.addFirst(475);

        // Displaying the existing ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque(Collection c) 
        // constructor
        ConcurrentLinkedDeque<Integer>
            cld1 = new ConcurrentLinkedDeque<Integer>(cld);

        // Displaying the existing ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque1: "
                           + cld1);
    }
}
```

**Output:**

```java
ConcurrentLinkedDeque: [475, 1009, 70, 12]
ConcurrentLinkedDeque1: [475, 1009, 70, 12]
```