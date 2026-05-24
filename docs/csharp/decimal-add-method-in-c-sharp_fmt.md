# Decimal.Add 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/decimal-add-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-add-method-in-c-sharp/)

此方法用于添加两个指定的十进制值。

## 语法与参数

**语法：**
`public static decimal Add(decimal a1, decimal a2);`

**参数：**
- `a1`：此参数指定要添加的第一个值。
- `a2`：此参数指定要添加的第二个值。

**返回值：**
返回 `a1` 和 `a2` 的十进制和。

## 异常情况

如果 `a1` 和 `a2` 的和小于 `Decimal.MinValue` 或大于 `Decimal.MaxValue`，该方法将抛出 `OverflowException`。

下面的程序说明了 `Decimal.Add(Decimal, Decimal)` 方法的使用。

## 示例 1

```cs
// C# program to demonstrate the
// Decimal.Add(Decimal, Decimal) 
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = .01m;
            Decimal a2 = .03m;

            // adding the two Decimal value
            // using Add() method;
            Decimal value = Decimal.Add(a1, a2);

            // Display the sum
            Console.WriteLine("Decimal Sum : {0}", value);
        }
        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
Decimal Sum : 0.04
```

## 示例 2：处理 OverflowException

```cs
// C# program to demonstrate the
// Decimal.Add(Decimal, Decimal)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 1.01m;
            Decimal a2 = Decimal.MaxValue;

            // adding the two Decimal value
            // using Add() method;
            Decimal value = Decimal.Add(a1, a2);

            // Display the sum
            Console.WriteLine("Decimal Sum : {0}", value);
        }
        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
Exception Thrown: System.OverflowException
```