# Java 中的 AtomicLongArray getAndAccumulate() 方法示例

> 原文：[https://www.geeksforgeeks.org/atomiclongarray-getandaccumulate-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandaccumulate-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLongArray.getAndAccumulate()` 是 Java 中的一个内置方法，它在将给定函数应用于当前值和给定值后，用结果自动更新 `AtomicLongArray` 的任何索引处的值，并返回前一个值。此方法接受要执行操作的原子数组的索引、执行操作的值和累加器函数作为参数。应用该函数时，索引处的当前值作为其第一个参数，给定的更新作为第二个参数。累加器函数应该没有副作用，因为当由于线程之间的争用导致尝试的更新失败时，它可以被重新应用。方法 `getAndAccumulate()` 与 `accumulateAndGet()` 类似，但前者在更新前返回值，后者在更新后返回值。

## 语法

```java
public final long getAndAccumulate(int i, long x, LongBinaryOperator accumulatorFunction)
```

## 参数

该函数接受三个参数：

*   `i` – 要进行更新的索引。
*   `x` – 与索引 `i` 处的值进行运算的值。
*   `accumulatorFunction` – 一个无副作用的双参数函数。

## 返回值

该函数返回更新前的值，类型为 `long`。

以下程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the getAndAccumulate() function

import java.util.concurrent.atomic.AtomicLongArray;
import java.util.function.LongBinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 4;

        // Value to make operation with value at idx
        long x = 5;

        // Declaring the accumulatorFunction
        LongBinaryOperator add = (u, v) -> u + v;

        // Updating the value at idx
        // applying getAndAccumulate
        long prev = arr.getAndAccumulate(idx, x, add);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before update is "
                           + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```java
The array : [1, 2, 3, 4, 5]
Value at index 4 before update is 5
The array after update : [1, 2, 3, 4, 10]
```

### 程序 2

```java
// Java program that demonstrates
// the getAndAccumulate() function

import java.util.concurrent.atomic.AtomicLongArray;
import java.util.function.LongBinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 0;

        // Value to make operation with value at idx
        long x = 6;

        // Declaring the accumulatorFunction
        LongBinaryOperator sub = (u, v) -> u - v;

        // Updating the value at idx
        // applying getAndAccumulate
        long prev = arr.getAndAccumulate(idx, x, sub);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before update is "
                           + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```java
The array : [1, 2, 3, 4, 5]
Value at index 0 before update is 1
The array after update : [-5, 2, 3, 4, 5]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndAccumulate-int-long-java.util.function.LongBinaryOperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndAccumulate-int-long-java.util.function.LongBinaryOperator-)