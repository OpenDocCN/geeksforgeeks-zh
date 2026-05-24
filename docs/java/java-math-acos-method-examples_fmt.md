# Java 数学 acos()方法，带示例

> 原文：[https://www.geeksforgeeks.org/java-math-acos-method-examples/](https://www.geeksforgeeks.org/java-math-acos-method-examples/)

`java.lang.Math.acos()` 返回 `0.0` 到 `π` 之间角度的弧余弦。弧形余弦也称为余弦的倒数。如果参数为 `NaN` 或其绝对值大于 `1`，则结果为 `NaN`。

## 语法

```java
public static double acos(double a)
```

**参数：**
`a`：其弧余弦将被返回的值。

**返回：**
此方法返回参数的弧余弦。

## 示例

展示 `java.lang.Math.acos()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.acos() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = Math.PI;

// Output is NaN, because Math.PI gives 3.141 value
        // greater than 1
        System.out.println(Math.acos(a));

// convert Math.PI to radians
        double b = Math.toRadians(a);

        System.out.println(Math.acos(b));

        double c = 1.0;
        double d = 0.0;
        double e = -1.0;
        double f = 1.5;

        System.out.println(Math.acos(c));
        System.out.println(Math.acos(d));
        System.out.println(Math.acos(e));

// value of f does not lie in between -1 and 1
       // so output is NaN
        System.out.println(Math.acos(f));
    }
}
```

## 输出

```java
NaN
1.5159376794536454
0.0
1.5707963267948966
3.141592653589793
NaN
```