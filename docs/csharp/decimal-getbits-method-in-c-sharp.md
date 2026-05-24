# 小数。C# 中的 GetBits()方法

> 原文:[https://www . geesforgeks . org/decimal-getbits-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-getbits-method-in-c-sharp/)

**小数。GetBits()方法**用于将 Decimal 的指定实例的值转换为其等效的二进制表示。

> **语法:**公共静态 int[] GetBits(十进制 d)；
> 这里，取浮点值进行转换。
> 
> **返回值:**此方法返回一个 32 位有符号整数数组，该数组有四个元素，包含 d 的二进制表示形式。

下面的程序说明了*小数的使用。GetBits()* 方法

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.GetBits() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        decimal value = 18446744073709551615M;

        // getting Equivalent bit
        // using GetBits() method
        int[] arr = Decimal.GetBits(value);

        // Display the element
        for (int i = 0; i < arr.Length; i++)
            Console.WriteLine("Bit[{0}] = {1, 10:X8}",
                                          i, arr[i]);
    }
}
```

**输出:**

```cs
Bit[0] =   FFFFFFFF
Bit[1] =   FFFFFFFF
Bit[2] =   00000000
Bit[3] =   00000000

```

**例 2:**

```cs
// C# program to demonstrate the
// Decimal.GetBits() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(Decimal.MaxValue);
        Console.WriteLine("");
        get(Decimal.MinValue);
    }

    // defining get() method
    public static void get(decimal value)
    {

        // getting Equivalent bit
        // using GetBits() method
        Console.WriteLine("Converted value of {0} is",
                                               value);
        int[] arr = Decimal.GetBits(value);

        // Display the element
        for (int i = 0; i < arr.Length; i++)
            Console.WriteLine("Bit[{0}] = {1, 10:X8}",
                                           i, arr[i]);
    }
}
```

**输出:**

```cs
Converted value of 79228162514264337593543950335 is
Bit[0] =   FFFFFFFF
Bit[1] =   FFFFFFFF
Bit[2] =   FFFFFFFF
Bit[3] =   00000000

Converted value of -79228162514264337593543950335 is
Bit[0] =   FFFFFFFF
Bit[1] =   FFFFFFFF
Bit[2] =   FFFFFFFF
Bit[3] =   80000000

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . getbits？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.getbits?view=netframework-4.7.2)