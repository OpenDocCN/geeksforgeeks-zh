# Java Guava Shorts.max() 方法，带示例

> 原文: [https://www.geeksforgeeks.org/java-guava-shorts-max-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-max-method-with-examples/)

`Shorts.max()` 是 [Guava 库](https://www.geeksforgeeks.org/guava-library-java/) 中 [`Shorts`](https://www.geeksforgeeks.org/shorts-class-guava-java/) 类的一种方法，用于查找数组中存在的最大值。此方法返回的值是指定数组中最大的 `short` 值。

## 语法

```java
public static short max(short... array)
```

## 参数

该方法取一个强制参数 `array`，它是一个非空的 `short` 值数组。

## 返回值

该方法返回一个 `short` 值，即指定数组中的最大值。

## 异常

如果数组为空，则该方法抛出 `IllegalArgumentException`。

下面的程序说明了上述方法的使用：

## 示例-1

```java
// Java code to show implementation of
// Guava's Shorts.max() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 2, 4, 6, 10, 0, -5, 15, 7 };

        // Using Shorts.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is : " + Shorts.max(arr));
    }
}
```

## 输出

```java
Maximum value is : 15
```

## 示例-2

```java
// Java code to show implementation of
// Guava's Shorts.max() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = {};

        // Using Shorts.max() method to get the
        // maximum value present in the array
        // This should raise "IllegalArgumentException"
        // as the array is empty
        System.out.println("Maximum value is : " + Shorts.max(arr));
    }
}
```

## 输出

```java
Exception in thread "main" java.lang.IllegalArgumentException
    at com.google.common.base.Preconditions.checkArgument(Preconditions.java:108)
    at com.google.common.primitives.Shorts.max(Shorts.java:254)
    at GFG.main(File.java:19)
```

## 参考

[https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#max-short...-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#max-short...-)