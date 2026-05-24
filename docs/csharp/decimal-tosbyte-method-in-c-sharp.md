# 小数。C# 中的 ToSByte()方法

> 原文:[https://www . geesforgeks . org/decimal-tosbyte-method in-c-sharp/](https://www.geeksforgeeks.org/decimal-tosbyte-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 8 位有符号整数。用户还可以使用显式赋值运算符将十进制值转换为 8 位整数。

> **语法:**公共静态字节 ToSByte(十进制值)；
> 
> 这里*值*是要转换的十进制数。
> 
> **返回值:**返回一个 8 位有符号整数，相当于指定的*值*。
> 
> **异常:**如果指定值小于*最小值*或大于*最大值*，此方法将给出*overoverover Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToSByte() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 127.5555M;
            Decimal dec2 = 04.2996m;

            // using Decimal.ToSByte(Decimal) Method
            sbyte val1 = Decimal.ToSByte(dec1);

            // using Decimal.ToSByte(Decimal) Method
            sbyte val2 = Decimal.ToSByte(dec2);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                             + "is : {0}", val1);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                             + "is : {0}",val2);

        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
The SByte value is : 127
The SByte value is : 4

```

**例 2:**

```cs
// C# program to demonstrate the
// Decimal.ToSByte() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // taking a decimal number
            // above the range of SByte
            Decimal dec1 = 129M;

            // Taking the maximum value
            // of Decimal
            Decimal dec2 = Decimal.MaxValue;

            // using Decimal.ToSByte(Decimal) Method
            // It will give error as decimal number
            // is above the range of SByte
            sbyte val1 = Decimal.ToSByte(dec1);

            // using Decimal.SByte(Decimal) Method
            // It will give error as Decimal.MaxValue
            // value is out of range from SByte
            int val2 = Decimal.ToSByte(dec2);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                              + "is : {0}",val1);

            // Printing the SByte value
            Console.WriteLine("The SByte value "
                           + "is : {0}",  val2);

        }

        catch (OverflowException e)
        {
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . tosbyte？视图=netcore-2.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tosbyte?view=netcore-2.2)