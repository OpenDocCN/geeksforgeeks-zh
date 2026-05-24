# 小数。C# 中的 Truncate()方法

> 原文:[https://www . geesforgeks . org/decimal-truncate-in-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-truncate-method-in-c-sharp/)

此方法用于通过丢弃任何小数位数来获取指定小数的整数位数。此方法通过删除小数点后的数字，将指定值舍入到最接近的整数。

> **语法:**公共静态十进制 Truncate(十进制 d)；
> 这里， *d* 是要截断的小数。
> 
> **返回值:**返回 *d* 向零舍入到最接近的整数的结果。

**示例:**

```cs
// C# program to demonstrate the
// Decimal.Truncate(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Taking decimal variables
            // having fractional part
            Decimal dec1 = 214748.78549M;
            Decimal dec2 = 21458565.2996m;

            // using Decimal.Truncate(Decimal) Method
            Decimal val1 = Decimal.Truncate(dec1);

            // using Decimal.Truncate(Decimal) Method
            Decimal val2 = Decimal.Truncate(dec2);

            // Printing the Integral part only
            Console.WriteLine("The integral part of "+
                                "dec1 is: {0}", val1);

            Console.WriteLine("The integral part of "+
                                "dec2 is: {0}", val2);
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
The integral part of dec1 is: 214748
The integral part of dec2 is: 21458565

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . truncate？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.truncate?view=netframework-4.7.2)