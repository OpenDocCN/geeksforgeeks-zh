# Double.IsInfinity() 方法

> 原文: [https://www.geeksforgeeks.org/double-isinfinity-method-in-c-sharp/](https://www.geeksforgeeks.org/double-isinfinity-method-in-c-sharp/)

在 C# 中，`Double.IsInfinity()` 是一种 `Double` 结构方法。此方法用于检查指定值是否计算为正无穷大或负无穷大。在执行一些数学运算时，有可能获得正无穷大或负无穷大的结果。例如：如果任何正值被零除，就会产生正无穷大。

## 语法
```cs
public static bool IsInfinity(double d);
```

## 参数
* `d`：是 `System.Double` 类型的双精度浮点数。

## 返回类型
该函数返回一个布尔值 `true`，如果指定值评估为正无穷大或负无穷大，否则返回 `false`。

## 示例
```
Input  : d = 10 / 0.0 
Output : True

Input  : d = 7.997e307 + 9.985e307
Output : True
```

## 注
* 如果任何浮点运算的结果超过 `Double.MaxValue` (即 1.79769313486232E+308) 被认为是正无穷大，如果结果小于 `Double.MinValue` (即 -1.79769313486232E+308) 被认为是负无穷大。
* 浮点运算返回 `Infinity` (正无穷大) 或 `-Infinity` (负无穷大) 以指示溢出情况。

## 代码：演示 Double.IsInfinity(double) 方法
```cs
// C# program to illustrate the
// Double.IsInfinity() Method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Dividing a Positive number by zero
        // results in positive infinity.
        double zero = 0.0;
        double value = 10.0;
        double result = value / zero;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Double.IsInfinity(result));

        // Result of any operation that
        // exceeds Double.MaxValue
        // (i.e 1.79769313486232E+308)
        // is Positive infinity
        result = Double.MaxValue + 9.985e307;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Double.IsInfinity(result));

        // Result of any operation that
        // is less than Double.MinValue
        // (i.e -1.79769313486232E+308)
        // is Negative infinity
        result = Double.MinValue - 9.985e307;

        // Printing result
        Console.WriteLine(result);

        // Check result using IsInfinity() Method
        Console.WriteLine(Double.IsInfinity(result));
    }
}
```

### 输出
```cs
Infinity
True
Infinity
True
-Infinity
True
```