# Decimal.ToOACurrency() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/decimal-tooacurrency-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-tooacurrency-method-in-c-sharp/)

`Decimal.ToOACurrency(Decimal)` 方法用于将指定的 `Decimal` 值转换为等效的 OLE 自动化货币值，该值包含在 64 位有符号整数中。

## 语法

```cs
public static long ToOACurrency(decimal value);
```

这里，需要 `decimal` 数进行转换。

## 返回值

该方法返回一个 64 位有符号整数，其中包含值的 OLE 自动化等价物。

下面的程序说明了 `Decimal.ToOACurrency()` 方法的使用。

## 示例

### 例 1

```cs
// C# program to demonstrate the
// Decimal.ToOACurrency() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Decimal curr = 40;

        // A 64-bit signed integer that contains
        // the OLE Automation equivalent of value.
        long value = Decimal.ToOACurrency(curr);

        // Display the HashCode
        Console.WriteLine("Equivalent long value is {0}", value);
    }
}
```

**输出：**

```cs
Equivalent long value is 400000
```

### 例 2

```cs
// C# program to demonstrate the
// Decimal.ToOACurrency() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        Console.WriteLine("Equivalent long value are respectivily");
        get(20);
        get(30);
        get(40);
        get(4294967295);
    }

    // defining get() method
    public static void get(decimal curr)
    {
        // getting Equivalent decimal value
        // using ToOACurrency() method
        long value = Decimal.ToOACurrency(curr);

        // Display the HashCode
        Console.WriteLine("{0}", value);
    }
}
```

**输出：**

```cs
Equivalent long value are respectivily
200000
300000
400000
42949672950000
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tooacurrency?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tooacurrency?view=netframework-4.7.2)