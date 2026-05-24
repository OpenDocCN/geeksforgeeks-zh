# C# 中的 Single.IsInfinity() 方法示例

> 原文：[https://www.geeksforgeeks.org/single-isinfinity-method-in-c-sharp-with-example/](https://www.geeksforgeeks.org/single-isinfinity-method-in-c-sharp-with-example/)

在 C# 中，`Single` 是一个结构体，`IsInfinity()` 是其方法。此方法用于检查指定的浮点值是否计算为正无穷大或负无穷大。在执行一些数学运算时，有可能获得正无穷大或负无穷大的结果。例如：如果任何正值被零除，就会产生正无穷大。

## 语法

```cs
public static bool IsInfinity(float f);
```

## 参数

`f`：是 `System.Single` 类型的单精度浮点数。

## 返回类型

如果指定值的计算结果为正无穷大或负无穷大，则该方法返回布尔值 `true`，否则返回 `false`。

## 示例

```cs
// C# program to illustrate the
// Single.IsInfinity(Single) 
// Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Dividing a Positive number by zero
        // results in positive infinity.
        float zero = 0.0f;
        float value = 10.0f;
        float result = value / zero;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Single.IsInfinity(result));

        // Result of any operation that
        // exceeds Single.MaxValue
        // is Positive infintity
        result = Single.MaxValue * 9.25f;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Single.IsInfinity(result));

        // Result of any operation that
        // is less than Single.MinValue
        // is Negative infintity
        result = Single.MinValue * 9.565f;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Single.IsInfinity(result));
    }
}
```

## 输出

```cs
Infinity
True
Infinity
True
-Infinity
True
```

## 注意

浮点运算返回 `Positive` 或 `Negative` 来表示溢出情况。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.isinfinity?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isinfinity?view=netstandard-2.1)