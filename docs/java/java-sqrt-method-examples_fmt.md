# Java sqrt()方法示例

> 原文:[https://www.geeksforgeeks.org/java-sqrt-method-examples/](https://www.geeksforgeeks.org/java-sqrt-method-examples/)

`java.lang.Math.sqrt()`返回作为参数传递给它的`double`类型值的平方根。如果参数是`NaN`或负数，那么结果就是`NaN`。如果参数为正无穷大，则结果为正无穷大。如果传递的参数是正零或负零，那么结果将与参数的结果相同。

## 语法

```java
public static double sqrt(double a)
```

参数：
`a`：需要返回其平方根的值。

返回：
此方法返回传递给它的参数的正平方根值。

## 例1

展示`java.lang.Math.sqrt()`方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.sqrt() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = 30;

        System.out.println(Math.sqrt(a));

        a = 45;

        System.out.println(Math.sqrt(a));

        a = 60;

        System.out.println(Math.sqrt(a));

        a = 90;

        System.out.println(Math.sqrt(a));
    }
}
```

输出：

```java
5.477225575051661
6.708203932499369
7.745966692414834
9.486832980505138
```

## 例2

展示参数为`NaN`或`POSITIVE_INFINITY`时`java.lang.Math.sqrt()`方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.sqrt() method
import java.lang.Math; // importing java.lang package

public class GFG {
    public static void main(String[] args)
    {
        double positiveInfinity = Double.POSITIVE_INFINITY;
        double negativeVal = -5;
        double nan = Double.NaN;
        double result;

        // Here argument is negative,
        // output will be NaN
        result = Math.sqrt(negativeVal);
        System.out.println(result);

        // Here argument is positive infinity,
        // output will also positive infinity
        result = Math.sqrt(positiveInfinity);
        System.out.println(result);

        // Here argument is NaN, output will be NaN
        result = Math.sqrt(nan);
        System.out.println(result);
    }
}
```

输出：

```java
NaN
Infinity
NaN
```