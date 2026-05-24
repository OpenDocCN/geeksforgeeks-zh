# 小数。C# 中的 ToSingle()方法

> 原文:[https://www . geesforgeks . org/decimal-to single-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-tosingle-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的单精度浮点数。这种方法会产生舍入误差，因为单精度浮点数的有效位数少于十进制数。

> **语法:**公共静态 float ToSingle(十进制 d)；
> 这里，d 是要转换的十进制数。
> 
> **返回值:**返回一个相当于 *d* 的单精度浮点数。

**示例:**

```cs
// C# program to demonstrate the
// Decimal.ToSingle(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 0.0000000000134563456789M;
            Decimal dec2 = 4589662514452860951234M;

            // using ToSingle(Decimal) Method
            float val1 = Decimal.ToSingle(dec1);

            // using ToSingle(Decimal) Method
            float val2 = Decimal.ToSingle(dec2);

            // Printing the float value
            Console.WriteLine("The float value "
                             + "is : {0}", val1);

            // Printing the float value
            Console.WriteLine("The float value "
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
The float value is : 1.345635E-11
The float value is : 4.589663E+21

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . to single？视图=netcore-2.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tosingle?view=netcore-2.2)