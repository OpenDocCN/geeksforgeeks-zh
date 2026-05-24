# 小数。C# 中的 ToInt16()方法

> 原文:[https://www . geesforgeks . org/decimal-to int 16-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-toint16-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 16 位有符号整数。用户还可以使用显式赋值运算符将十进制值转换为 16 位整数。

> **语法:**公共静态短 ToInt16(十进制值)；
> 这里*值*是要转换的小数。
> 
> **返回值:**返回一个 16 位有符号整数，相当于指定的*值*。
> 
> **异常:**如果指定值小于*最小值*或大于*最大值*，此方法将给出*overoverover Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToInt16(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 21564.236M;
            Decimal dec2 = 32767.256m;

            // using Decimal.ToInt16(Decimal) Method
            // Here short means Int16
            short val1 = Decimal.ToInt16(dec1);

            // using Decimal.ToInt16(Decimal) Method
            // Here short means Int16
            short val2 = Decimal.ToInt16(dec2);

            // Printing the Int16 value
            Console.WriteLine("The Int16 value "
                              + "is : {0}", val1);

            // Printing the Int16 value
            Console.WriteLine("The Int16 value "
                              + "is : {0}", val2);

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
The Int16 value is : 21564
The Int16 value is : 32767

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.ToInt16(Decimal) Method
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

            // using Decimal.ToInt16(Decimal) Method
            // Here short means Int16
            // It will give error as Decimal.MaxValue
            // value is out of range from Int16
            short val1 = Decimal.ToInt16(dec1);

            // Printing the Int16 value
            Console.WriteLine("The Int16 value "
                              + "is : {0}", val1);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . to int 16？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.toint16?view=netframework-4.7.2)