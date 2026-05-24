# Java 中 doubleToLongBits() 方法详解

> 原文：[https://www.geeksforgeks.org/double-doubletolongbits-method-in-java-with-examples/](https://www.geeksforgeks.org/double-doubletolongbits-method-in-java-with-examples/)

[`java.lang.Double`](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 `doubleToLongBits()` 方法是 Java 中的内置函数，根据 IEEE 754 浮点“双格式”位布局返回指定浮点值的表示。

## 语法

```java
public static long doubleToLongBits(double val)
```

## 参数

该方法只接受一个参数 `val`，用于指定双精度浮点数。

## 返回值

函数返回代表浮点数的位。以下是一些特例：

*   如果参数为正无穷大，则结果为 `0x7ff0000000000000L`。
*   如果参数为负无穷大，则结果为 `0xfff0000000000000L`。
*   如果参数是 `NaN`，结果是 `0x7ff8000000000000L`。

## 示例

下面的程序说明了 `Double.doubleToLongBits()` 方法的使用：

### 程序 1

```java
// Java program to demonstrate
// Double.doubleToLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = 1.5d;

        // function call
        long answer = Double.doubleToLongBits(val);

        // print
        System.out.println(val + " in long bits: "
                           + answer);
    }
}
```

**输出：**

```java
1.5 in long bits: 4609434218613702656
```

### 程序 2

```java
// Java program to demonstrate
// Double.doubleToLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = Double.POSITIVE_INFINITY;
        double val1 = Double.NEGATIVE_INFINITY;
        double val2 = Double.NaN;

        // function call
        long answer = Double.doubleToLongBits(val);

        // print
        System.out.println(val + " in long bits: "
                           + answer);

        // function call
        answer = Double.doubleToLongBits(val1);

        // print
        System.out.println(val1 + " in long bits: "
                           + answer);

        // function call
        answer = Double.doubleToLongBits(val2);

        // print
        System.out.println(val2 + " in long bits: "
                           + answer);
    }
}
```

**输出：**

```java
Infinity in long bits: 9218868437227405312
-Infinity in long bits: -4503599627370496
NaN in long bits: 9221120237041090560
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#doubleToLongBits(double)](https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#doubleToLongBits(double))