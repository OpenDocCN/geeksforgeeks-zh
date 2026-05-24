# Java 数学 hypot()方法示例

> 原文: [https://www.geeksforgeeks.org/java-math-hypot-method-example/](https://www.geeksforgeeks.org/java-math-hypot-method-example/)

`java.lang.Math.hypot()` 函数是 Java 中一个内置的数学函数，返回欧几里德范数，![ \sqrt{(x * x + y * y)} ](img/20660befd2bf5ed8109f5dda9f36b24f.png "Rendered by QuickLaTeX.com")。该函数返回 `sqrt(x^2 + y^2)`，没有中间溢出或下溢。

*   如果任一参数为无穷大，则结果为正无穷大。
*   如果任一参数为 `NaN`，且任一参数都不是无穷大，则结果为 `NaN`。

## 语法

```java
public static double hypot(double x, double y)
```

参数：
`x` 和 `y` 是数值。

## 返回

`sqrt(x^2 + y^2)` 无中间上溢或下溢。

## 例 1

展示 `java.lang.Math.hypot()` 方法的工作原理。

```java
// Java program to demonstrate working
// of java.lang.Math.hypot() method
import java.lang.Math;

class Gfg {

    // Driver code
    public static void main(String args[])
    {
        double x = 3;
        double y = 4;

        // when both are not infinity
        double result = Math.hypot(x, y);
        System.out.println(result);

        double positiveInfinity =
               Double.POSITIVE_INFINITY;
        double negativeInfinity =
               Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;

        // when 1 or more argument is NAN
        result = Math.hypot(nan, y);
        System.out.println(result);

        // when both arguments are infinity
        result = Math.hypot(positiveInfinity,
                            negativeInfinity);
        System.out.println(result);
    }
}
```

## 输出

```java
5.0
NaN
Infinity
```