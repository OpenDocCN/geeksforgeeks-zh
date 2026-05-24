# 小数。C# 中的 `FromOACurrency()` 方法

> 原文：[https://www.geeksforgeeks.org/decimal-fromoacurrency-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-fromoacurrency-method-in-c-sharp/)

`Decimal.FromOACurrency()` 方法用于将包含 OLE 自动化货币值的指定 64 位有符号整数转换为等效的十进制值。

## 语法
```cs
public static decimal FromOACurrency(long cy);
```
这里，它需要一个 OLE 自动化货币值。

## 返回值
该方法返回一个 `Decimal`，其中包含 `cy` 的等价物。

下面的程序说明了 `Decimal.FromOACurrency(Int64)` 方法的使用：

## 例 1
```cs
// C# program to demonstrate the
// Decimal.FromOACurrency() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        long curr = long.MaxValue;

        // getting Equivalent decimal value
        // using FromOACurrency() method
        decimal value = Decimal.FromOACurrency(curr);

        // Display the value
        Console.WriteLine("Equivalent decimal " +
                        "value is {0}", value);
    }
}
```
**输出：**
```
Equivalent decimal value is 922337203685477.5807
```

## 例 2
```cs
// C# program to demonstrate the
// Decimal.FromOACurrency() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        Console.WriteLine("Equivalent decimal value" +
                                " are respectively");
        get(long.MaxValue);
        get(long.MinValue);
        get(1234567890987654321);
        get(4294967295L);
    }

    // defining get() method
    public static void get(long curr)
    {
        // getting Equivalent decimal value
        // using FromOACurrency() method
        decimal value = Decimal.FromOACurrency(curr);

        // Display the value
        Console.WriteLine("{0}", value);
    }
}
```
**输出：**
```
Equivalent decimal value are respectively
922337203685477.5807
-922337203685477.5808
123456789098765.4321
429496.7295
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.fromoacurrency?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.fromoacurrency?view=netframework-4.7.2)