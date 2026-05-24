# c# 中的十进制结构

> 原文:[https://www.geeksforgeeks.org/decimal-struct-in-c-sharp/](https://www.geeksforgeeks.org/decimal-struct-in-c-sharp/)

在 C# 中，`Decimal` Struct 类用于表示十进制浮点数。十进制数的范围是+79,228,162,514,264,337,593,543,950,335 到-79,228,162,514,264,337,593,543,950,335。由于其范围广泛，它通常用于需要大量有效整数和小数位数且无舍入误差的金融计算。您还可以对十进制类型执行数学运算，如加法、减法、除法、乘法等。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `Decimal(Double)` | 将 `Decimal` 的新实例初始化为指定的双精度浮点数的值。 |
| `Decimal(Int32)` | 将 `Decimal` 的新实例初始化为指定的 32 位有符号整数的值。 |
| `Decimal(Int32[])` | 将 `Decimal` 的新实例初始化为以二进制表示并包含在指定数组中的十进制值。 |
| `Decimal(Int64)` | 将 `Decimal` 的新实例初始化为指定的 64 位有符号整数的值。 |
| `Decimal(Single)` | 将 `Decimal` 的新实例初始化为指定的单精度浮点数的值。 |
| `Decimal(UInt32)` | 将 `Decimal` 的新实例初始化为指定的 32 位无符号整数的值。 |
| `Decimal(UInt64)` | 将 `Decimal` 的新实例初始化为指定的 64 位无符号整数的值。 |
| `Decimal(Int32, Int32, Int32, Boolean, Byte)` | 从指定实例组成部分的参数初始化 `Decimal` 的新实例。 |

## 字段

| 字段 | 描述 |
| --- | --- |
| `MaxValue` | 表示十进制的最大可能值。该字段是常量和只读的。 |
| `MinusOne` | 表示负数 1(-1)。 |
| `MinValue` | 表示小数的最小可能值。该字段是常量和只读的。 |
| `One` | 代表数字一(1)。 |
| `Zero` | 表示数字零(0)。 |

**示例:**

```cs
// C# program to illustrate the
// use of MaxValue and MinValue field
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Display the Minimum and Maximum values
        Console.WriteLine("Display Maximum value "+ 
              "of Decimal: {0}", Decimal.MaxValue);

        Console.WriteLine("Display Minimum value of "+
                    "Decimal: {0}", Decimal.MinValue);
    }
}
```

**Output:**

```cs
Display Maximum value of Decimal: 79228162514264337593543950335
Display Minimum value of Decimal: -79228162514264337593543950335
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(Decimal, Decimal)` | 添加两个指定的十进制值。 |
| `Ceiling(Decimal)` | 返回大于或等于指定十进制数的最小整数值。 |
| `Compare(Decimal, Decimal)` | 比较两个指定的十进制值。 |
| `CompareTo()` | 将此实例与指定的对象或小数进行比较，并返回它们的相对值的指示。 |
| `Divide(Decimal, Decimal)` | 将两个指定的十进制值相除。 |
| `Equals()` | 返回一个值，该值指示 `Decimal` 的两个实例是否表示相同的值。 |
| `Floor(Decimal)` | 将指定的十进制数向负无穷大舍入到最接近的整数。 |
| `FromOACurrency(Int64)` | 将包含 OLE 自动化货币值的指定 64 位有符号整数转换为等效的十进制值。 |
| `GetBits(Decimal)` | 将指定的 `Decimal` 实例的值转换为其等效的二进制表示形式。 |
| `GetHashCode()` | 返回此实例的哈希代码。 |
| `GetTypeCode()` | 返回十进制值类型的类型代码。 |
| `Multiply(Decimal, Decimal)` | 将两个指定的十进制值相乘。 |
| `Negate(Decimal)` | 返回指定的十进制值乘以负一的结果。 |
| `Parse()` | 将数字的字符串表示形式转换为其十进制等价形式。 |
| `Remainder(Decimal, Decimal)` | 在除以两个十进制值后计算余数。 |
| `Round()` | 将值舍入到最接近的整数或指定的小数位数。 |
| `Subtract(Decimal, Decimal)` | 从另一个指定的十进制值中减去一个。 |
| `ToByte(Decimal)` | 将指定的十进制值转换为等效的 8 位无符号整数。 |
| `ToDouble(Decimal)` | 将指定的十进制值转换为等效的双精度浮点数。 |
| `ToInt16(Decimal)` | 将指定的十进制值转换为等效的 16 位有符号整数。 |
| `ToInt32(Decimal)` | 将指定的十进制值转换为等效的 32 位有符号整数。 |
| `ToInt64(Decimal)` | 将指定的十进制值转换为等效的 64 位有符号整数。 |
| `ToOACurrency(Decimal)` | 将指定的十进制值转换为等效的 OLE 自动化货币值，该值包含在 64 位有符号整数中。 |
| `ToSByte(Decimal)` | 将指定的十进制值转换为等效的 8 位有符号整数。 |
| `ToSingle(Decimal)` | 将指定的十进制值转换为等效的单精度浮点数。 |
| `ToString()` | 将此实例的数值转换为其等效的字符串表示形式。 |
| `ToUInt16(Decimal)` | 将指定的十进制值转换为等效的 16 位无符号整数。 |
| `ToUInt32(Decimal)` | 将指定的十进制值转换为等效的 32 位无符号整数。 |
| `ToUInt64(Decimal)` | 将指定的十进制值转换为等效的 64 位无符号整数。 |
| `Truncate(Decimal)` | 返回指定小数的整数位数；任何小数位数都将被丢弃。 |
| `TryParse()` | 将数字的字符串表示形式转换为其十进制等价形式。返回值指示转换是成功还是失败。 |

**示例:**

```cs
// C# program to illustrate the
// use of Add(Decimal, Decimal)
// method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Addition of two Decimal values
        // Using Add() method
        Decimal val1 = 349;
        Decimal val2 = 590;
        Decimal result;
        result = Decimal.Add(val1, val2);

        // Display the result
        Console.WriteLine("Addition is: {0}", result);
    }
}
```

**Output:**

```cs
Addition is: 939
```

## 运算符

| 运算符 | 描述 |
| --- | --- |
| `Addition(Decimal, Decimal)` | 添加两个指定的十进制值。 |
| `Decrement(Decimal)` | 将十进制操作数减 1。 |
| `Division(Decimal, Decimal)` | 将两个指定的十进制值相除。 |
| `Equality(Decimal, Decimal)` | 返回一个值，该值指示两个十进制值是否相等。 |
| `Explicit(Single to Decimal)` | 定义单精度浮点数到十进制数的显式转换。 |
| `Explicit(Double to Decimal)` | 定义双精度浮点数到十进制数的显式转换。 |
| `Explicit(Decimal to Int32)` | 定义小数到 32 位无符号整数的显式转换。 |
| `Explicit(Decimal to Int16)` | 定义十进制到 16 位无符号整数的显式转换。 |
| `Explicit(Decimal to Single)` | 定义小数到单精度浮点数的显式转换。 |
| `Explicit(Decimal to SByte)` | 定义小数到 8 位有符号整数的显式转换。 |
| `Explicit(Decimal to UInt64)` | 定义小数到 64 位无符号整数的显式转换。 |
| `Explicit(Decimal to Int32)` | 定义小数到 32 位有符号整数的显式转换。 |
| `Explicit(Decimal to Int16)` | 定义十进制到 16 位有符号整数的显式转换。 |
| `Explicit(Decimal to Double)` | 定义小数到双精度浮点数的显式转换。 |
| `Explicit(Decimal to Char)` | 定义十进制到 Unicode 字符的显式转换。 |
| `Explicit(Decimal to Byte)` | 定义小数到 8 位无符号整数的显式转换。 |
| `Explicit(Decimal to Int64)` | 定义小数到 64 位有符号整数的显式转换。 |
| `GreaterThan(Decimal, Decimal)` | 返回一个值，该值指示指定的小数是否大于另一个指定的小数。 |
| `GreaterThanOrEqual(Decimal, Decimal)` | 返回一个值，该值指示指定的小数是否大于或等于另一个指定的小数。 |
| `Implicit(UInt32 to Decimal)` | 定义 32 位无符号整数到十进制数的隐式转换。 |
| `Implicit(UInt16 to Decimal)` | 定义 16 位无符号整数到十进制数的隐式转换。 |
| `Implicit(Byte to Decimal)` | 定义 8 位有符号整数到十进制的隐式转换。 |
| `Implicit(Int64 to Decimal)` | 定义 64 位有符号整数到十进制的隐式转换。 |
| `Implicit(SByte to Decimal)` | 定义 8 位无符号整数到十进制数的隐式转换。 |
| `Implicit(Int16 to Decimal)` | 定义 16 位有符号整数到十进制的隐式转换。 |
| `Implicit(Char to Decimal)` | 定义 Unicode 字符到十进制的隐式转换。 |
| `Implicit(UInt64 to Decimal)` | 定义 64 位无符号整数到十进制数的隐式转换。 |
| `Implicit(Int32 to Decimal)` | 定义 32 位有符号整数到十进制的隐式转换。 |
| `Increment(Decimal)` | 将十进制操作数增加 1。 |
| `Inequality(Decimal, Decimal)` | 返回一个值，该值指示两个十进制对象是否具有不同的值。 |
| `LessThan(Decimal, Decimal)` | 返回一个值，该值指示指定的小数是否小于另一个指定的小数。 |
| `LessThanOrEqual(Decimal, Decimal)` | 返回一个值，该值指示指定的小数是否小于或等于另一个指定的小数。 |
| `Modulus(Decimal, Decimal)` | 返回两个指定的十进制值相除后的余数。 |
| `Multiply(Decimal, Decimal)` | 将两个指定的十进制值相乘。 |
| `Subtraction(Decimal, Decimal)` | 减去两个指定的十进制值。 |
| `UnaryNegate(Decimal)` | 否定指定的十进制操作数的值。 |
| `UnaryPlus(Decimal)` | 返回十进制操作数的值(操作数的符号不变)。 |

**示例:**

```cs
// C# program to illustrate the
// use of Decrement and Increment
// operator
using System;

class GFG {

    static public void Main()
    {
        Decimal myval1 = 1000;
        Decimal myval2 = 10000;

        // Using Decrement operator we decrease myval1 by 1
        Console.WriteLine("My value 1 is: {0}", myval1);
        Console.WriteLine("Decrease myval1 by 1:{0}", --myval1);
        Console.WriteLine();

        // Using Increment operator we increase myval2 by 1
        Console.WriteLine("My value 2 is: {0}", myval2);
        Console.WriteLine("Increase myval2 by 1:{0}", ++myval2);
    }
}
```

**Output:**

```cs
My value 1 is: 1000
Decrease myval1 by 1:999

My value 2 is: 10000
Increase myval2 by 1:10001
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal?view=netframework-4.7.2)