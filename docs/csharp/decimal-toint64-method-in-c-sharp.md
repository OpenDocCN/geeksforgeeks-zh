# 小数。C# 中的 ToInt64()方法

> 原文:[https://www . geesforgeks . org/decimal-to int 64-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-toint64-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 64 位有符号整数。用户还可以使用显式赋值运算符将十进制值转换为 64 位整数。

> **语法:**公共静态长 ToInt64(十进制 d)；
> 
> 这里*值*是要转换的十进制数。
> 
> **返回值:**返回一个 64 位有符号整数，相当于指定的*值*。
> 
> **异常:**如果指定值小于*最小值*或大于*最大值*，此方法将给出*overoverover Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToInt64(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = -926534668654775808.859m;
            Decimal dec2 = 4897498545.2364654M;

            // using Decimal.ToInt64(Decimal) Method
            // Here long means Int64
            long val1 = Decimal.ToInt64(dec1);

            // using Decimal.ToInt64(Decimal) Method
            // Here long means Int64
            long val2 = Decimal.ToInt64(dec2);

            // Printing the Int64 value
            Console.WriteLine("The Int64 value "
                            + "is : {0}", val1);

            // Printing the Int64 value
            Console.WriteLine("The Int64 value "
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
The Int64 value is : -926534668654775808
The Int64 value is : 4897498545

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.ToInt64(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = Decimal.MinValue;

            // Taking the maximum value 
            // of Decimal
            Decimal dec2 = Decimal.MaxValue;

            // using Decimal.ToInt64(Decimal) Method
            // Here long means Int64
            // It will give error
            long val1 = Decimal.ToInt64(dec1);

            // using Decimal.ToInt64(Decimal) Method
            // Here long means Int64
            // It will give error
            long val2 = Decimal.ToInt64(dec2);

            // Printing the Int64 value
            Console.WriteLine("The Int64 value "
                            + "is : {0}", val1);

            // Printing the Int64 value
            Console.WriteLine("The Int64 value "
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
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . toint 64？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.toint64?view=netframework-4.7.2)