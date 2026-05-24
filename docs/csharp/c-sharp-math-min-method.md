# C# |数学。最小()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-min-method/](https://www.geeksforgeeks.org/c-sharp-math-min-method/)

在 C# 中， ***Min()*** 是一个数学类方法，返回两个指定数字中较小的一个。该方法总是采用两个参数，并且可以通过*将传递的参数的数据类型*更改如下来重载:

*   **数学。Min(字节，字节):**返回两个 8 位无符号整数中较小的一个。
*   **数学。最小值(十进制，十进制):**返回两个十进制数中较小的一个。
*   **数学。Min(Double，Double):** 返回两个双精度浮点数中较小的一个。
*   **数学。Min(Int16，Int16):** 返回两个 16 位有符号整数中较小的一个。这里 *Int16* 是*的简称*数据类型。
*   **数学。Min(Int32，Int32):** 返回两个 32 位有符号整数中较小的一个。这里 *Int32* 是 *int* 数据类型。
*   **数学。Min(Int64，Int64):** 返回两个 64 位有符号整数中较小的一个。这里 *Int64* 是*长*的数据类型。
*   **数学。最小值(字节，字节):**返回两个 8 位有符号整数中较小的一个。
*   **数学。Min(single，single):** 返回两个单精度浮点数中较小的一个。这里*单*是*浮动*数据类型。
*   **数学。Min(UInt16，UInt16):** 返回两个 16 位无符号整数中较小的一个。这里 *UInt16* 是*无符号短(ushort)* 数据类型。
*   **数学。Min(UInt32，UInt32):** 返回两个 32 位无符号整数中较小的一个。这里 *UInt32* 是*无符号整数(uint)* 数据类型。
*   **数学。Min(UInt64，UInt64):** 返回两个 64 位无符号整数中较小的一个。这里 *UInt64* 是*无符号长(ulong)* 数据类型。

**上述所有方法的通用语法:**

```cs
public static data_type Min(Data_type first_value, Data_type second_value)
```

**参数:**

> 这些方法总是接受指定数据类型的两个参数。

**返回类型:**方法返回参数列表中指定的两个数字的最小值，返回类型取决于传递的参数类型。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Math.Min() method
using System;
class GFG {

// Main Method
static void Main()
{

    // byte data type
    byte b1 = 10, b2 = 15;

    // decimal data type
    decimal d1 = 1000M, d2 = 1568M;

    // double data type
    double db1 = 15.896745, db2 = 8.62644598;

    // Int16 data type
    short sh1 = -96, sh2 = 24;

    // Int32 data type
    int i1 = 26745236, i2 = 36725413;

    // Int64 data type
    long l1 = -2534234234234, l2 = -745837587527423;

    // sbyte data type
    sbyte sb1 = 52, sb2 = 120;

    // single data type
    float f1 = 8.0f, f2 = 78.78f;

    // UInt16 data type
    ushort us1 = 5346, us2 = 6437;

    // UInt32 data type
    uint un1 = 432344637, un2 = 64762738;

    // UInt64 data type
    ulong ul1 = 34234234, ul2 = 673286478326;

    // displaying result
    Console.WriteLine("Math.Min Method (Byte, Byte) = " + Math.Min(b1, b2));
    Console.WriteLine("Math.Min Method (Decimal, Decimal) = " + Math.Min(d1, d2));
    Console.WriteLine("Math.Min Method (Double, Double) = " + Math.Min(db1, db2));
    Console.WriteLine("Math.Min Method (Int16, Int16) = " + Math.Min(sh1, sh2));
    Console.WriteLine("Math.Min Method (Int32, Int32) = " + Math.Min(i1, i2));
    Console.WriteLine("Math.Min Method (Int64, lInt64) = " + Math.Min(l1, l2));
    Console.WriteLine("Math.Min Method (SByte, SByte) = " + Math.Min(sb1, sb2));
    Console.WriteLine("Math.Min Method (Single, Single) = " + Math.Min(f1, f2));
    Console.WriteLine("Math.Min Method (UInt16, UInt16) = " + Math.Min(us1, us2));
    Console.WriteLine("Math.Min Method (UInt32, UInt32) = " + Math.Min(un1, un2));
    Console.WriteLine("Math.Min Method (UInt64, UInt64) = " + Math.Min(ul1, ul2));

    }
}
```

**Output:** 

```cs
Math.Min Method (Byte, Byte) = 10
Math.Min Method (Decimal, Decimal) = 1000
Math.Min Method (Double, Double) = 8.62644598
Math.Min Method (Int16, Int16) = -96
Math.Min Method (Int32, Int32) = 26745236
Math.Min Method (Int64, lInt64) = -745837587527423
Math.Min Method (SByte, SByte) = 52
Math.Min Method (Single, Single) = 8
Math.Min Method (UInt16, UInt16) = 5346
Math.Min Method (UInt32, UInt32) = 64762738
Math.Min Method (UInt64, UInt64) = 34234234
```