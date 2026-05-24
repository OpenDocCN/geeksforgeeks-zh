# Java Math getExponent() 方法，带示例

> 原文: [https://www.geeksforgeeks.org/java-math-getexponent-method-example/](https://www.geeksforgeeks.org/java-math-getexponent-method-example/)

`java.lang.Math.getExponent()` 返回双精度或浮点表示中使用的无偏指数。

**注:**

*   如果参数是双精度或浮点类型的 `NaN` 或 `无穷大`，则 `结果` 为 (`Double.MAX_EXPONENT + 1`) 或 (`Float.MAX_EXPONENT + 1`)。
*   如果参数是双精度或浮点型的 `零` 或 `次常规`，则 `结果` 为 (`Double.MIN_EXPONENT - 1`) 或 (`Float.MIN_EXPONENT - 1`)。

**语法:**

```java
public static int getExponent(DataType a)
```

参数:
`a` : 一个 `double` 或 `float` 类型的参数

返回:
此方法返回参数的无偏指数。

```java
// Java program to demonstrate working
// of java.lang.Math.getExponent() method
import java.lang.Math;

class Gfg {

// driver code
    public static void main(String args[])
    {
        double a = 345.65;
        double b = 1.0 / 0;
        double c = 0;

// Input double value
        // Output unbiased exponent of it
        System.out.println(Math.getExponent(a));

// Input Infinity
        // Output (Double.MAX_EXPONENT + 1)
        System.out.println(Math.getExponent(b));

// Input Zero
        // Output (Double.MIN_EXPONENT - 1)
        System.out.println(Math.getExponent(c));

        float d = 237.2f;
        float e = 1.0f / 0;
        float f = 0f;

// Input float value
        // Output unbiased exponent of it
        System.out.println(Math.getExponent(d));

// Input Infinity
        // Output (Float.MAX_EXPONENT + 1)
        System.out.println(Math.getExponent(e));

// Input Zero
        // Output (Float.MIN_EXPONENT - 1)
        System.out.println(Math.getExponent(f));
    }
}
```

**输出:**

```java

```