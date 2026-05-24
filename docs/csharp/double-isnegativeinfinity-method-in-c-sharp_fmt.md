# C# 中的 Double.IsNegativeInfinity() 方法

> 原文：[https://www.geeksforgeeks.org/double-isnegativeinfinity-method-in-c-sharp/](https://www.geeksforgeeks.org/double-isnegativeinfinity-method-in-c-sharp/)

在 C# 中，`Double` 是一个结构体方法。此方法用于检查指定值是否计算为负无穷大。在某些浮点运算中，有可能获得负无穷大的结果。*例如：* 如果任何负值被零除，就会产生负无穷大。

> **语法：** `public static bool IsNegativeInfinity(double d);`
> **参数：**
> `d`：是 `System.Double` 类型的双精度浮点数。

**返回类型：** 该函数返回一个布尔值 `true`，如果指定值计算为负无穷大，否则返回 `false`。

**示例：**

```cs
Input  : d = -5.0 / 0.0 
Output : True

Input  : d = -1.5935e250 * 7.948e110
Output : True
```

**代码：** 演示 `Double.IsNegativeInfinity(Double)` 方法

## C# 代码示例

```cs
// C# program to illustrate the
// Double.IsNegativeInfinity() Method
using System;

class GFG {

// Main method
    static public void Main()
    {

// Dividing a negative number by zero
        // results in Negative infinity.

// Dividing a number directly by 0
        // produces an error
        // So 0 is stored in a variable first

double zero = 0.0;
        double value = -5;
        double result = value / zero;

// Printing result
        Console.WriteLine(result);

// Check result using IsNegativeInfinity() Method
        Console.WriteLine(Double.IsNegativeInfinity(result));

// Result of floating point operation
        // that is less than Double.MinValue
        // is Negative Infinity

result = Double.MinValue * 7.948e110;

// Printing result
        Console.WriteLine(result);

// Check result using IsNegativeInfinity() Method
        Console.WriteLine(Double.IsNegativeInfinity(result));
    }
}
```

**输出：**

```cs
-Infinity
True
-Infinity
True
```

**注意：**

*   任何浮点运算的结果都小于 `Double.MinValue`（即 -1.7976931348623157E+308）被认为是负无穷大。
*   浮点运算返回 `Infinity`（正无穷大）或 `-Infinity`（负无穷大）以指示溢出情况。