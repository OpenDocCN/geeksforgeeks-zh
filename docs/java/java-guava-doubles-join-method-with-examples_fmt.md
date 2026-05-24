# Doubles.join()方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-doubles-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-join-method-with-examples/)

番石榴库中 [`Doubles`](https://www.geeksforgeeks.org/doubles-class-guava-java/) 类的 `join()` 方法用于组合或连接由`separator`分隔的所有给定的`double`值。这些`double`值被传递给这个方法一个参数。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定的`double`值进行连接操作的结果。

> **例如：**`join("-", 1.0, 2.0, 3.0)`返回字符串`"1.0-2.0-3.0"`。

## 语法

> `public static String join(String separator, double... array)`

## 参数

该方法接受两个强制参数：

*   `separator`：是出现在连接的`double`值之间的分隔符。
*   `array`：是要连接的`double`值数组。

## 返回值

这个方法返回一个包含所有给定`double`值的字符串，用`separator`分隔。

下面的程序说明了这种方法的使用：

## 例1

```java
// Java code to show implementation of
// Guava's Doubles.join() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a double array
        double[] arr = { 2.3, 4.2, 6.2, 8.6, 10.5 };

        // Using Doubles.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Doubles.join("#", arr));
    }
}
```

**Output：**

```java
2.3#4.2#6.2#8.6#10.5
```

## 例2

```java
// Java code to show implementation of
// Guava's Doubles.join() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a double array
        double[] arr = { 3.2, 5.4, 7.6, 9.1, 11.2 };

        // Using Doubles.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Doubles.join("*", arr));
    }
}
```

**Output：**

```java
3.2*5.4*7.6*9.1*11.199999809265137
```

**参考：**[https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#join(java.lang.String, %20double...)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#join(java.lang.String, %20double...))