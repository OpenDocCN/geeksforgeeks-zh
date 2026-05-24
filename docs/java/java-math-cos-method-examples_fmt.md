# Java Math cos() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/java-math-cos-method-examples/](https://www.geeksforgeeks.org/java-math-cos-method-examples/)

`java.lang.Math.cos()` 方法返回一个角度的三角余弦值。如果参数是 `NaN` 或无穷大，则返回的结果是 `NaN`。返回值将在范围 `[-1, 1]` 内。

## 语法

```java
public static double cos(double angle)
```

**参数：**
该函数有一个必需的参数 `angle`，单位为弧度。

## 返回值
函数返回一个角度的三角余弦值。

## 示例 1
展示 `java.lang.Math.cos()` 方法的工作原理。

```java
// Java program to demonstrate working
// of java.lang.Math.cos() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = 30;

// converting values to radians
        double b = Math.toRadians(a);

        System.out.println(Math.cos(b));

        a = 45;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.cos(b));

        a = 60;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.cos(b));

        a = 0;

// converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.cos(b));
    }
}
```

**输出：**

```java
0.8660254037844387
0.7071067811865476
0.5000000000000001
1.0
```

## 示例 2
展示当自变量为 `NaN` 或无穷大时，`java.lang.Math.cos()` 方法的工作情况。

```java
// Java program to demonstrate working
// of java.lang.Math.cos() method infinity case
import java.lang.Math; // importing java.lang package

public class GFG {
    public static void main(String[] args)
    {

        double positiveInfinity =
               Double.POSITIVE_INFINITY;
        double negativeInfinity =
               Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;
        double result;

// Here argument is negative infinity,
        // output will be NaN
        result = Math.cos(negativeInfinity);
        System.out.println(result);

// Here argument is positive infinity,
        // output will also be NaN
        result = Math.cos(positiveInfinity);
        System.out.println(result);

// Here argument is NaN, output will be NaN
        result = Math.cos(nan);
        System.out.println(result);
    }
}
```

**输出：**

```java
NaN
NaN
NaN
```