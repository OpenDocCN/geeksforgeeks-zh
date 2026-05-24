# Java 中的 AtomicIntegerArray addAndGet() 方法示例

> 原文：[https://www.geeksforgeeks.org/atomicintegerarray-addandget-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-addandget-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicIntegerArray.addAndGet()` 是 Java 中的一个内置方法，它在 `AtomicIntegerArray` 的指定索引处自动给元素添加给定值。此方法将索引值和要添加的值作为参数，并返回此索引处的更新值。

## 语法

```java
public int addAndGet(int i, int delta)
```

## 参数

该函数接受两个参数：

*   `i` – 要添加值的索引。
*   `delta` – 要添加的值。

## 返回值

该函数返回更新后的值，该值在 `int` 中。

## 示例

以下程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the addAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 10, 22, 33, 44, 55 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where value is to be added
        int idx = 0;

        // Value to add with value at idx
        int x = 16;

        // Updating the value at
        // idx applying addAndGet
        arr.addAndGet(idx, x);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```
The array : [10, 22, 33, 44, 55]
The array after update : [26, 22, 33, 44, 55]
```

### 程序 2

```java
// Java program that demonstrates
// the addAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where value is to be added
        int idx = 3;

        // Value to add with value at idx
        int x = 16;

        // Updating the value at
        // idx applying addAndGet
        arr.addAndGet(idx, x);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 20, 5]
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#addAndGet(int, %20int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#addAndGet(int, %20int))