# Java Math nextUp()方法示例

> 原文: [https://www.geeksforgeeks.org/java-math-nextup-method-examples/](https://www.geeksforgeeks.org/java-math-nextup-method-examples/)

`java.lang.Math.nextUp()` 是 Java 中的一个内置数学函数，它返回与正无穷大方向提供的参数相邻的浮点值。`nextUp()` 方法重载，这意味着我们在 `Math` 类下有多个同名的方法。`nextUp()` 的两个重载方法：

*   **双型:** `nextUp(double d)`
*   **浮动类型:** `nextUp(float f)`

**注:**

*   如果参数是 `NaN`，那么结果就是 `NaN`。
*   如果参数为 `零`，则结果为 `Double.MIN_VALUE`（如果我们处理的是 `double`），如果是 `float`，那么结果就是 `Float.MIN_VALUE`。
*   如果参数为 `正无穷大`，则结果为 `正无穷大`。

## 语法

```java
public static dataType nextUp(dataType g)
```

参数：
`g`：起始浮点值的输入。

返回：
`nextUp()` 方法返回更接近正无穷大的相邻浮点值。

## 示例

展示 `java.lang.Math.nextUp()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.nextUp() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double g = 69.19;

// Input double value, Output adjacent floating-point
        System.out.println(Math.nextUp(g));

float gf = 78.1f;

// Input float value, Output adjacent floating-point
        System.out.println(Math.nextUp(gf));

double a = 0.0 / 0;

// Input NaN, Output NaN
        System.out.println(Math.nextUp(a));

float b = 0.0f;

// Input zero, Output Float.MIN_VALUE for float
        System.out.println(Math.nextUp(b));

double c = 1.0 / 0;

// Input positive infinity, Output positive infinity
        System.out.println(Math.nextUp(c));
    }
}
```

**输出:**

```java
69.19000000000001
78.100006
NaN
1.4E-45
Infinity
```