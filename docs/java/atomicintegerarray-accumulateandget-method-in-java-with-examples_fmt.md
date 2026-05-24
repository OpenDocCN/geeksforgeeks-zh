# Java 中的 AtomicIntegerArray `accumulateAndGet()` 方法示例

> 原文：[https://www.geeksforgeeks.org/atomicintegerarray-accumulateandget-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-accumulateandget-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicIntegerArray.accumulateAndGet()` 是 Java 中的一个内置方法，它会用给定函数应用于当前值和给定值的结果自动更新索引 `i` 处的元素，并返回更新后的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。该函数的第一个参数是索引 `i` 处的当前值，第二个参数是给定的更新。

## 语法

```java
public final int accumulateAndGet(int i, int x, IntBinaryOperator accumulatorFunction)
```

## 参数

该函数接受三个参数：
*   `i` – 要更新的索引。
*   `x` – 与索引 `i` 处的值进行运算的值。
*   `accumulatorFunction` – 一个无副作用的双参数函数。

## 返回值

该函数返回更新后的值，类型为 `int`。

以下程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the accumulateAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;
import java.util.function.IntBinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 4;

        // Value to make operation with value at idx
        int x = 5;

        // Declaring the accumulatorFunction
        IntBinaryOperator add = (u, v) -> u + v;

        // Updating the value at idx
        // applying accumulatorFunction
        arr.accumulateAndGet(idx, x, add);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 4, 10]
```

### 程序 2

```java
// Java program that demonstrates
// the accumulateAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;
import java.util.function.IntBinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 17, 22, 33, 44, 55 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 0;

        // Value to make operation with value at idx
        int x = 6;

        // Declaring the accumulatorFunction
        IntBinaryOperator sub = (u, v) -> u - v;

        // Updating the value at idx
        // applying accumulatorFunction
        arr.accumulateAndGet(idx, x, sub);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出：**

```java
The array : [17, 22, 33, 44, 55]
The array after update : [11, 22, 33, 44, 55]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndAccumulate-int-int-java.util.function.IntBinaryOperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndAccumulate-int-int-java.util.function.IntBinaryOperator-)