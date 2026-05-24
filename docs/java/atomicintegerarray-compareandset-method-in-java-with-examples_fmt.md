# Java 中的 AtomicIntegerArray compareAndSet() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomicintegerarray-compareandset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-compareandset-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicIntegerArray.compareAndSet()` 是 Java 中的一个内置方法，如果当前值等于预期值，它会自动将某个位置的元素设置为给定的更新值。此方法将索引值、预期值和更新值作为参数，并返回一个布尔值，说明该值是否已更新。

## 语法

```java
public final boolean compareAndSet(int i, int expect, int update)
```

## 参数

该函数接受三个参数：

*   `i`：要进行操作的索引。
*   `expect`：期待值，检查是否等于当前值。
*   `update`：需要更新的值。

## 返回值

该函数返回一个布尔值，说明该值是否已成功更新。如果成功则返回 `true`，否则返回 `false`，表示当前值不等于期望值。

以下程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the compareAndSet() function

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

        // Index where operation is performed
        int idx = 3;

        // Value to expect at idx
        int expect = 4;

        // Value to update if current value
        // is equal to expected value
        int update = 40;

        // Updating the value at idx
        // applying compareAndSet
        arr.compareAndSet(idx, expect, update);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 40, 5]
```

### 程序 2

```java
// Java program that demonstrates
// the compareAndSet() function

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

        // Index where operation is performed
        int idx = 3;

        // Value to expect at idx
        int expect = 40;

        // Value to update if current value
        // is equal to expected value
        int update = 4;

        // Updating the value at
        // idx applying compareAndSet
        arr.compareAndSet(idx, expect, update);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 4, 5]
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#compareAndSet(int, %20int, %20int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#compareAndSet(int, %20int, %20int))