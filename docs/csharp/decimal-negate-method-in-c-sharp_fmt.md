# C# 中的 Decimal.Negate() 方法

> 原文：[Decimal.Negate(Decimal) Method in C#](https://www.geeksforgeeks.org/decimal-negate-method-in-c-sharp/)

此方法用于获取指定的十进制值乘以负一的结果。

## 语法

```cs
public static decimal Negate(decimal a);
```

## 参数

- `a`：该参数指定将要转换的小数。

## 返回值

一个十进制数，数值为 `a`，但符号相反。但是零，如果 `a` 是零。

## 示例

下面的程序说明了 `Decimal.Negate(Decimal)` 方法的使用：

### 例 1：当 `a` 为正时

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring the decimal variable
        Decimal a = 127.97m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the negative value
        Console.WriteLine("The negative value "+
                          "is : {0}", value);
    }
}
```

**输出：**

```cs
The negative value is : -127.97
```

### 例 2：当 `a` 为负时

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring the decimal variable
        Decimal a = -12.39m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the value after
        // using negate method
        Console.WriteLine("The value is : {0}", value);
    }
}
```

**输出：**

```cs
The value is : 12.39
```

### 例 3：如果 `a` 为零

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring the decimal variable
        Decimal a = 0.00m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the Negate value
        Console.WriteLine("The Negate value "+
                          "is : {0}", value);
    }
}
```

**输出：**

```cs
The Negate value is : 0.00
```

## 参考

- [Decimal.Negate(Decimal) Method (System)](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.negate?view=netframework-4.7.2)