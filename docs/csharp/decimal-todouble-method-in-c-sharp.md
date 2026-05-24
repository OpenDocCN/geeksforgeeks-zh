# 小数。C# 中的 Double()方法

> 原文:[https://www . geesforgeks . org/decimal-to double-method in-c-sharp/](https://www.geeksforgeeks.org/decimal-todouble-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的双精度浮点数。这种方法会产生舍入误差，因为双精度浮点数的有效位数少于十进制数。

> **语法:**公共静态 double ToDouble(十进制 d)；
> 这里，d 是要转换的十进制值。
> 
> **返回值:**返回一个相当于 *d* 的双精度浮点数。

**示例:**

```cs
// C# program to demonstrate the
// Decimal.ToDouble(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            Decimal dec1 = 0.0000000000134563456789M;
            Decimal dec2 = 4589662514452860951234M;

            // using ToDouble(Decimal) Method
            Double val1 = Decimal.ToDouble(dec1);

            // using ToDouble(Decimal) Method
            Double val2 = Decimal.ToDouble(dec2);

            // Printing the Double value
            Console.WriteLine("The Double value "
                              + "is : {0}", val1);

            // Printing the Double value
            Console.WriteLine("The Double value "
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
The Double value is : 1.34563456789E-11
The Double value is : 4.58966251445286E+21

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . to double？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.todouble?view=netframework-4.7.2)