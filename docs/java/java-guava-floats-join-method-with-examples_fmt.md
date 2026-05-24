# Java 番石榴 | `Floats.join()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/java-guava-floats-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-join-method-with-examples/)

番石榴库中 [`Floats`](https://www.geeksforgeeks.org/floats-class-guava-java/) 类的 `join()` 方法用于组合或连接由**分隔符**分隔的所有给定的 `float` 值。这些浮点值被作为参数传递给这个方法。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定浮点值进行联接操作的结果。

> **例如：** `join("-", 1.0f, 2.0f, 3.0f)` 返回字符串 `"1.0-2.0-3.0"`。

## 语法

```java
public static String join(String separator, float... array)
```

## 参数

该方法接受两个强制参数：

*   `separator`：是出现在连接的浮点值之间的分隔符字符。
*   `array`：是要连接的浮点值数组。

## 返回值

这个方法返回一个包含所有给定浮点值的字符串，用 `separator` 分隔。

下面的程序说明了这种方法的使用：

## 示例 1

```java
// Java code to show implementation of
// Guava's Floats.join() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 2.3f, 4.2f, 6.2f, 8.6f, 10.5f };

        // Using Floats.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Floats.join("#", arr));
    }
}
```

**输出：**

```java
2.3#4.2#6.2#8.6#10.5
```

## 示例 2

```java
// Java code to show implementation of
// Guava's Floats.join() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 3.2f, 5.4f, 7.6f, 9.1f, 11.2f };

        // Using Floats.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Floats.join("*", arr));
    }
}
```

**输出：**

```java
3.2*5.4*7.6*9.1*11.2
```

## 参考

[https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#join(java.lang.String, %20float...)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#join(java.lang.String, %20float...))