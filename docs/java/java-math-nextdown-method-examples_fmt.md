# Java Math nextDown() 方法，带示例

> 原文: [https://www.geeksforgeeks.org/java-math-nextdown-method-examples/](https://www.geeksforgeeks.org/java-math-nextdown-method-examples/)

`java.lang.Math.nextDown()` 是 Java 中的一个内置数学函数，它返回的浮点值与负无穷大方向上提供的参数相邻。`nextDown()` 的实现可能比其等价的 `nextAfter()` 调用运行得更快。`nextDown()` 方法是重载的，这意味着我们在 `Math` 类下有多个同名的方法。`nextDown()` 的两个重载方法：

*   **双精度型:** `nextDown(double d)`
*   **浮点型:** `nextDown(float f)`

**注:**

*   如果参数是 `NaN`，那么结果就是 `NaN`。
*   如果参数为 `零`，则结果为 `-Double.MIN_VALUE`（如果我们处理的是 `double`），如果是 `float`，那么结果就是 `-Float.MIN_VALUE`。
*   如果参数为 `负无穷大`，则结果为 `负无穷大`。

**语法:**

```java
public static dataType nextDown(dataType g)
```

参数：
`g`：起始浮点值的输入。

返回值：
`nextDown()` 方法返回更接近负无穷大的相邻浮点值。

**示例:** 展示 `java.lang.Math.nextDown()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.nextDown() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double g = 23.44;

// Input double value, Output adjacent floating-point
        System.out.println(Math.nextDown(g));

float gf = 28.1f;

// Input float value, Output adjacent floating-point
        System.out.println(Math.nextDown(gf));

double a = 0.0 / 0;

// Input NaN, Output NaN
        System.out.println(Math.nextDown(a));

float b = 0.0f;

// Input zero, Output - Float.MIN_VALUE for float
        System.out.println(Math.nextDown(b));

double c = -1.0 / 0;

// Input negative infinity, Output negative infinity
        System.out.println(Math.nextDown(c));
    }
}
```

**输出:**

```java
23.439999999999998
28.099998
NaN
-1.4E-45
-Infinity
```