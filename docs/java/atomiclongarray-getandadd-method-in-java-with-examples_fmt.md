# Java 中的 AtomicLongArray getAndAdd()方法，示例

> 原文: [https://www.geeksforgeeks.org/atomiclongarray-getandadd-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandadd-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLongArray.getAndAdd()`是 Java 中的一个内置方法，它在 `AtomicLongArray` 的指定索引处自动将给定的值添加到元素中。此方法将 `AtomicLongArray` 的索引值和要添加的值作为参数，并在添加操作之前返回该值。方法 `getAndAdd()` 与 `addAndGet()` 类似，但前者返回加法运算前的值，后者返回加法运算后的值。

## 语法

```java
public final long getAndAdd(int i, long delta)
```

## 参数

该方法接受两个参数:
*   `i` – 要添加值的索引。
*   `delta` – 要添加的值。

## 返回值

该方法返回加法运算前的值，类型为 `long`。

以下程序说明上述方法:

### 程序 1

```java
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 10, 22, 33, 44, 55 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where value is to be added
        int idx = 0;

        // Value to add with value at idx
        long x = 16;

        // Updating the value at
        // idx applying getAndAdd and
        // storing the previous value
        long prev = arr.getAndAdd(idx, x);

        // Previous value at index idx
        // before update
        System.out.println("Value at index " + idx
                           + " before update is " + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [10, 22, 33, 44, 55]
Value at index 0 before update is 10
The array after update : [26, 22, 33, 44, 55]
```

### 程序 2

```java
// Java program that demonstrates
// the getAndAdd() function

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

        // Index where value is to be added
        int idx = 3;

        // Value to add with value at idx
        long x = 16;

        // Updating the value at
        // idx applying getAndAdd and
        // storing the previous value
        long prev = arr.getAndAdd(idx, x);

        // Previous value at index idx
        // before update
        System.out.println("Value at index " + idx
                           + " before update is "
                           + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
Value at index 3 before update is 4
The array after update : [1, 2, 3, 20, 5]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndAdd-int-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndAdd-int-long-)