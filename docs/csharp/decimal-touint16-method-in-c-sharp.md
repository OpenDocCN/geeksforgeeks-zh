# 小数。C# 中的 ToUInt16()方法

> 原文:[https://www . geesforgeks . org/decimal-touint 16-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-touint16-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 16 位无符号整数。用户还可以使用显式赋值运算符将十进制值转换为 16 位无符号整数。

> **语法:**公共静态 ushort ToUInt16(十进制值)；
> 这里*值*是要转换的小数。
> 
> **返回值:**返回一个 16 位无符号整数，相当于指定的*值*。
> 
> **异常:**如果指定值小于*最小值*或大于*最大值*，此方法将给出*overoverover Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToUInt16(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 65535.458M;
            Decimal dec2 = 32768.256m;

            // using Decimal.ToUInt16(Decimal) Method
            ushort val1 = Decimal.ToUInt16(dec1);

            // using Decimal.ToUInt16(Decimal) Method
            ushort val2 = Decimal.ToUInt16(dec2);

            // Printing the UInt16 value
            Console.WriteLine("The UInt16 value "
                             + "is : {0}", val1);

            // Printing the UInt16 value
            Console.WriteLine("The UInt16 value "
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
The UInt16 value is : 65535
The UInt16 value is : 32768

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.ToUInt16(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variable
            // Taking the maximum value
            // of Decimal
            Decimal dec1 = Decimal.MaxValue;

            // using Decimal.ToUInt16(Decimal) Method
            // It will give error as Decimal.MaxValue
            // value is out of range from UInt16
            ushort val1 = Decimal.ToUInt16(dec1);

            // Printing the UInt16 value
            Console.WriteLine("The UInt16 value "
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . touint 16？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.touint16?view=netframework-4.7.2)