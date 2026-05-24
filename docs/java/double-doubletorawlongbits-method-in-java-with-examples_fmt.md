# Java 中 Double 类的 `doubleToRawLongBits()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/double-doubletorawlongbits-method-in-java-with-examples/](https://www.geeksforgeeks.org/double-doubletorawlongbits-method-in-java-with-examples/)

[`Double`](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 `doubleToRawLongBits()` 方法是 Java 中的内置函数，根据 IEEE 754 浮点“双格式”位布局返回指定浮点值的表示形式，保留非数字（NaN）值。

## 语法

```java
public static long doubleToRawLongBits(double val)
```

## 参数

该方法只接受一个指定双精度浮点数的参数 `val`。

## 返回值

函数返回代表浮点数的位。以下是一些特例：

*   如果参数为正无穷大，则结果为 `0x7ff0000000000000L`。
*   如果参数为负无穷大，则结果为 `0xfff0000000000000L`。
*   如果参数是 `NaN`，结果是 `0x7ff8000000000000L`。

下面的程序说明了 `Double.doubleToRawLongBits()` 方法的使用：

### 程序 1

```java
// Java program to demonstrate
// Double.doubleToRawLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = 1.5d;

        // function call
        long answer = Double.doubleToRawLongBits(val);

        // print
        System.out.println(val + " in raw long bits: "
                           + answer);
    }
}
```

**输出：**

```java
1.5 in raw long bits: 4609434218613702656
```

### 程序 2

```java
// Java program to demonstrate
// Double.doubleToRawLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = Double.POSITIVE_INFINITY;
        double val1 = Double.NEGATIVE_INFINITY;
        double val2 = Double.NaN;

        // function call
        long answer = Double.doubleToRawLongBits(val);

        // print
        System.out.println(val + " in raw long bits: "
                           + answer);

        // function call
        answer = Double.doubleToRawLongBits(val1);

        // print
        System.out.println(val1 + " in raw long bits: "
                           + answer);

        // function call
        answer = Double.doubleToRawLongBits(val2);

        // print
        System.out.println(val2 + " in raw long bits: "
                           + answer);
    }
}
```

**输出：**

```java
Infinity in raw long bits: 9218868437227405312
-Infinity in raw long bits: -4503599627370496
NaN in raw long bits: 9221120237041090560
```

**参考：**[https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#doubleToRawLongBits(double)](https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#doubleToRawLongBits(double))