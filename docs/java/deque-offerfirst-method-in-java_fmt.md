# Java 中的 Deque offerFirst()方法

> 原文: [https://www.geeksforgeeks.org/deque-offerfirst-method-in-java/](https://www.geeksforgeeks.org/deque-offerfirst-method-in-java/)

`offerFirst(E e)` 方法在 [`Deque`](https://www.geeksforgeeks.org/deque-interface-java-example/) 接口中将指定的元素插入到双端队列的前面，如果有可能的话，在不违反容量限制的情况下立即插入。此方法优于 `addFirst()` 方法，因为此方法在容器容量满时不会抛出异常，因为它返回 `false`。

## 语法

```java
boolean offerFirst(E e)
```

## 参数

此方法接受一个强制参数 `e`，它是要插入到双端队列前面的元素。

## 返回

该方法在成功插入时返回 `true`，否则返回 `false`。

## 异常

函数抛出四个异常，描述如下：

*   `ClassCastException`：当要输入元素的类阻止其被添加到此容器时抛出。
*   `IllegalArgumentException`：当元素的某些属性阻止其被添加到 `Deque` 时抛出。
*   `NullPointerException`：当要插入的元素作为 `null` 传递，且 `Deque` 接口不允许 `null` 元素时抛出。

下面的程序说明了 `offerFirst()` 的方法：

### 程序 1

```java
// Java Program Demonstrate offerFirst()
// method of Deque when Null is passed
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {
        // create object of Deque
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>(3);

        if (DQ.offerFirst(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerFirst(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerFirst(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerFirst(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is full
Deque: [25, 15, 10]
```

### 程序 2

```java
// Java Program Demonstrate offerFirst()
// method of Queue when Null is passed
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws NullPointerException
    {
        // create object of Queue
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Deque
        DQ.offerFirst(7855642);
        DQ.offerFirst(35658786);
        DQ.offerFirst(5278367);

        // when null is inserted
        DQ.offerFirst(null);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出：**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerFirst(LinkedBlockingDeque.java:342)
    at GFG.main(GFG.java:21)
```

**注意：** 另外两个异常是内部异常，是由编译器导致的，因此不能在代码中显示。

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#offerFirst-E-](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#offerFirst-E-)