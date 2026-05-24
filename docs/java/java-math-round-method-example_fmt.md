# Java Math.round() 方法带示例

> 原文: `https://www.geeksforgeeks.org/java-math-round-method-example/`

`java.lang.Math.round()` 是一个内置的数学函数，它返回与参数最接近的 `long` 型整数。通过将 `1/2` 相加，将结果舍入为整数，在相加 `1/2` 后取结果的下限，并将结果转换为 `long` 型。

*   如果参数为 `NaN`，则结果为 `0`。
*   如果参数为负无穷大或任何小于或等于 `Integer.MIN_VALUE` 的值，结果等于 `Integer.MIN_VALUE` 的值。
*   如果参数为正无穷大或大于或等于 `Integer.MAX_VALUE` 的值，结果等于 `Integer.MAX_VALUE` 的值。

## 语法

```java
public static int round(float val)
```

参数：
`val` - 要舍入为整数的浮点值。

## 返回值

该方法返回舍入到最接近 `int` 值的参数值。

## 示例

展示 `java.lang.Math.round()` 函数的工作原理。

```java
// Java program to demonstrate working
// of java.lang.Math.round() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        // float numbers
        float x = 4567.9874f;

        // find the closest int for these floats
        System.out.println(Math.round(x));

        float y = -3421.134f;

        // find the closest int for these floats
        System.out.println(Math.round(y));

        double positiveInfinity = Double.POSITIVE_INFINITY;

        // returns the Integer.MAX_VALUE value when
        System.out.println(Math.round(positiveInfinity));

    }
}
```

## 输出

```java
4568
-3421
2147483647
```