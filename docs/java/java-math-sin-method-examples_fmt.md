# Java Math.sin()方法示例

> 原文: [https://www.geeksforgeeks.org/java-math-sin-method-examples/](https://www.geeksforgeeks.org/java-math-sin-method-examples/)

`java.lang.Math.sin()` 返回 0.0 到 π 之间的三角正弦值。如果参数是 `NaN` 或无穷大，那么结果就是 `NaN`。如果该参数为零，则结果是一个零，其符号与该参数相同。返回值将介于 -1 和 1 之间。

## 语法:

```java
public static double sin(double a);
```

**参数**: 要返回正弦值的值。

**返回类型**: 此方法返回参数的正弦值。

## 实施

在这里，我们将提出两个例子，其中一个简单地展示 `Math.sin()` 方法的基本工作，另一个展示边界情况。

## 示例 1: 基本用法

```java
// Java program to demonstrate working
// of java.lang.Math.sin() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = 30;

// converting values to radians
        double b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 45;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 60;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 90;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));
    }
}
```

**输出:**

```java
0.49999999999999994
0.7071067811865475
0.8660254037844386
1.0
```

## 示例 2: 边界情况

```java
// Java program to demonstrate working of Math.cos() method
// of java.lang package considering infinity case

// Importing classes from java.lang package
import java.lang.Math;

public class GFG {

// Main driver method
    public static void main(String[] args)
    {

        double positiveInfinity = Double.POSITIVE_INFINITY;
        double negativeInfinity = Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;
        double result;

// Here argument is negative infinity,
        // output will be NaN
        result = Math.sin(negativeInfinity);
        System.out.println(result);

// Here argument is positive infinity,
        // output will also be NaN
        result = Math.sin(positiveInfinity);
        System.out.println(result);

// Here argument is NaN, output will be NaN
        result = Math.sin(nan);
        System.out.println(result);
    }
}
```

**输出:**

```java
NaN
NaN
NaN
```