# 小数。C# 中的 ToInt32()方法

> 原文:[https://www . geesforgeks . org/decimal-to int 32-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-toint32-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 32 位有符号整数。用户还可以使用显式赋值运算符将十进制值转换为 32 位整数。

> **语法:**公共静态 int ToInt32(十进制值)；
> 
> 这里*值*是要转换的十进制数。
> 
> **返回值:**返回一个 32 位有符号整数，相当于指定的*值*。
> 
> **异常:**如果指定值小于*最小值*或大于*最大值*，此方法将给出*overoverover Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToInt32(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 2147483647M;
            Decimal dec2 = 21458565.2996m;

            // using Decimal.ToInt32(Decimal) Method
            // Here int means Int32
            int val1 = Decimal.ToInt32(dec1);

            // using Decimal.ToInt32(Decimal) Method
            // Here int means Int32
            int val2 = Decimal.ToInt32(dec2);

            // Printing the Int32 value
            Console.WriteLine("The Int32 value "
                            + "is : {0}", val1);

            // Printing the Int32 value
            Console.WriteLine("The Int32 value "
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
The Int32 value is : 2147483647
The Int32 value is : 21458565

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.ToInt32(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            // taking a decimal number 
            // above the range of Int32
            Decimal dec1 = 2147483648M;

            // Taking the maximum value 
            // of Decimal
            Decimal dec2 = Decimal.MaxValue;

            // using Decimal.ToInt32(Decimal) Method
            // Here int means Int32
            // It will give error as decimal number 
            // is above the range of Int32
            int val1 = Decimal.ToInt32(dec1);

            // using Decimal.ToInt32(Decimal) Method
            // Here int means Int32
            // It will give error as Decimal.MaxValue
            // value is out of range from Int32
            int val2 = Decimal.ToInt32(dec2);

            // Printing the Int32 value
            Console.WriteLine("The Int32 value "
                            + "is : {0}", val1);

            // Printing the Int32 value
            Console.WriteLine("The Int32 value "
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . toint 32？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.toint32?view=netframework-4.7.2)