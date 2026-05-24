# 小数。C# 中的 ToUInt64()方法

> 原文:[https://www . geesforgeks . org/decimal-touint 64-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-touint64-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 64 位无符号整数。用户还可以使用显式赋值运算符将十进制值转换为 64 位无符号整数。

> **语法:**公共静态 ulong ToUInt64(十进制 d)；
> 
> 这里 *d* 是要转换的十进制数。
> 
> **返回值:**返回一个 64 位无符号整数，相当于指定值，即 *d* 。
> 
> **异常:**如果指定值为负值或大于*最大值*，该方法将给出*overoverowexception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToUInt64(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 9223372036854775807.999m;
            Decimal dec2 = 18446744073709551615.784m;

            // using Decimal.ToUInt64(Decimal) Method
            ulong val1 = Decimal.ToUInt64(dec1);

            // using Decimal.ToUInt64(Decimal) Method
            ulong val2 = Decimal.ToUInt64(dec2);

            // Printing the UInt64 value
            Console.WriteLine("The UInt64 value "
                             + "is : {0}", val1);

            // Printing the UInt64 value
            Console.WriteLine("The UInt64 value "
                             + "is : {0}", val2);

        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
The UInt64 value is : 9223372036854775807
The UInt64 value is : 18446744073709551615

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.ToUInt64(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking the maximum value
            // of Decimal
            Decimal dec1 = Decimal.MaxValue;

            // using Decimal.ToUInt64(Decimal) Method
            // It will give error as decimal number
            // is above the range of UInt64
            ulong val1 = Decimal.ToUInt64(dec1);

            // Printing the UInt64 value
            Console.WriteLine("The UInt64 value "
                               + "is : {0}",val1);                           
        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . touint 64？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.touint64?view=netframework-4.7.2)