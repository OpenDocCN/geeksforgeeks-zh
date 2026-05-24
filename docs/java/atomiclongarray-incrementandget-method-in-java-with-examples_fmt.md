# Java 中的 AtomicLongArray incrementAndGet()方法，示例

> 原文：[https://www.geeksforgeeks.org/atomiclongarray-incrementandget-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-incrementandget-method-in-java-with-examples/)

## 方法介绍

`java.util.concurrent.atomic.AtomicLongArray.incrementAndGet()` 是 Java 中的一个内置方法，它会自动将 `AtomicLongArray` 的任何索引处的值递增 1。该方法将 `AtomicLongArray` 的索引值作为参数，在该索引处递增该值，并返回递增后的值。函数 `incrementAndGet()` 类似于 `getAndIncrement()` 函数，但是前者返回增量后的值，而后者返回增量操作前的值。

## 语法

```java
public final long incrementAndGet(int i)
```

## 参数

该函数接受单个参数 `i`，该参数是执行一次递增操作的索引。

## 返回值

该函数返回增量操作后的值，该值在 `long` 内。

下面的程序说明了上述方法：

## 程序 1

```java
// Java program that demonstrates
// the incrementAndGet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Updating the value at
        // idx applying incrementAndGet
        arr.incrementAndGet(idx);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 5, 5]
```

## 程序 2

```java
// Java program that demonstrates
// the incrementAndGet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Updating the value at
        // idx applying incrementAndGet
        arr.incrementAndGet(idx);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [11, 12, 13, 14, 15]
The array after update : [12, 12, 13, 14, 15]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#incrementAndGet-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#incrementAndGet-int-)