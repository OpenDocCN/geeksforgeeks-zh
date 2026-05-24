# Java 中的 AtomicLongArray lazySet()方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomiclongarray-lazyset-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-lazyset-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLongArray.lazySet()`是 Java 中的一个内置方法，它最终会在`AtomicLongArray`的任何给定索引处设置一个给定值。该方法将`AtomicLongArray`的索引值和要设置的值作为参数，并在不返回任何内容的情况下更新以前的值。

## 语法

> `public final void lazySet(int i, long newValue)`

## 参数

函数取两个参数：
*   `i` 是要进行更新的索引值。
*   `newValue` 是要在索引处更新的新值。

## 返回值

函数不返回值。

## 程序 1

下面的程序说明了上述方法：

```java
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray
        // with array a
        AtomicLongArray arr
            = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // The new value to update at idx
        long val = 10;

        // Updating the value at
        // idx applying lazySet
        arr.lazySet(idx, val);

        // Displaying the AtomicLongArray
        System.out.println("The array after"
                           + " update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [10, 2, 3, 4, 5]
```

## 程序 2

```java
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray
        // with array a
        AtomicLongArray arr
            = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // The new value to update at idx
        long val = 100;

        // Updating the value at
        // idx applying lazySet
        arr.lazySet(idx, val);

        // Displaying the AtomicLongArray
        System.out.println("The array after "
                           + "update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 100, 5]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#lazySet-int-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#lazySet-int-long-)