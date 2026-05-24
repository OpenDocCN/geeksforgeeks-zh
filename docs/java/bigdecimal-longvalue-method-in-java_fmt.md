# Java 中的 BigDecimal longValue()方法

> 原文: [https://www.geeksforgeeks.org/bigdecimal-longvalue-method-in-java/](https://www.geeksforgeeks.org/bigdecimal-longvalue-method-in-java/)

`BigDecimal.longValue()` 是一个内置函数，它将这个 `BigDecimal` 转换成一个 `long` 值。该函数丢弃这个 `BigDecimal` 的任何小数部分。当转换结果太大而无法表示为 `long` 值时，该函数仅返回低阶 64 位。

## 语法

```java
public long longValue()
```

## 参数

此功能不接受参数。

## 返回值

该函数返回这个 `BigDecimal` 的 `long` 值。

## 例

```java
Input : 1987812456121.176
Output : 1987812456121

Input : "721111"
Output : 721111
```

下面的程序说明了 `java.math.BigDecimal.longValue()` 方法的使用。

## 程序 1

```java
// Java program to illustrate
// longValue() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;

        // Assigning values to b1, b2
        b1 = new BigDecimal("1987812456121.176");
        b2 = new BigDecimal("721111");

        // Displaying their respective Long Values
        System.out.println("The Long Value of " + b1 +
        " is " + b1.longValue());
        System.out.println("The Long Value of " + b2 +
        " is " + b2.longValue());
    }
}
```

## 输出

```java
The Long Value of 1987812456121.176 is 1987812456121
The Long Value of 721111 is 721111
```

## 注意

关于 `BigDecimal` 的整体幅度和精度的信息，该 `BigDecimal` 值可能会在该函数的转换过程中丢失。因此，可能会返回符号相反的结果。

## 程序 2

下面的程序说明了函数返回一个符号相反的结果的场景。

```java
// Java program to illustrate
// longValue() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;

        // Assigning values to b1, b2
        b1 = new BigDecimal("267694723232435121868");
        b2 = new BigDecimal("72111184561789104423");

        // Displaying their respective Long Values
        System.out.println("The Long Value of " + b1 +
        " is " + b1.longValue());
        System.out.println("The Long Value of " + b2 +
        " is " + b2.longValue());
    }
}
```

## 输出

```java
The Long Value of 267694723232435121868 is -9006437873208152372
The Long Value of 72111184561789104423 is -1675791733049102041
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#longValue()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#longValue())