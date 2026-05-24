# C# | BitConverter。双 to t64 位()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-double toint 64 bits-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-doubletoint64bits-method/)

**BitConverter。Double to t64 bits(Double)方法**用于将指定的双精度浮点数转换为 64 位有符号整数。

**语法:**

```cs
public static long DoubleToInt64Bits (double value);
```

这里*值*是要转换的数字。

**返回值:**该方法返回一个 64 位有符号整数，其值相当于*值*。

以下程序说明了**位转换器的使用。双 to t64 位(双)**方法:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.DoubleToInt64Bits()
// Method
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing double value
        double value = 1.2345678901234565;

        // Display the double value
        Console.Write("double-precision floating point: ");
        Console.WriteLine("{0}", value);
        Console.WriteLine();

        // Converting double to long value
        // using BitConverter.DoubleToInt64Bits()
        // Method
        long value1 = BitConverter.DoubleToInt64Bits(value);

        // Display the 64-bit signed integer.
        Console.Write("64-bit signed integer: ");
        Console.WriteLine("{0}", value1);
    }
}
```

**Output:**

```cs
double-precision floating point: 1.23456789012346

64-bit signed integer: 4608238818662570490

```

**例 2:**

```cs
// C# program to demonstrate
// BitConverter.DoubleToInt64Bits()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing double value
        double value = 1.0;

        // Display the double value
        Console.Write("double-precision floating point: ");
        Console.WriteLine("{0}", value);
        Console.WriteLine();

        // Converting double to long value
        // using BitConverter.DoubleToInt64Bits()
        // Method
        long value1 = BitConverter.DoubleToInt64Bits(value);

        // Display the 64-bit signed integer.
        Console.Write("64-bit signed integer: ");
        Console.WriteLine("{0}", value1);
        Console.WriteLine();

        // Display the Hexadecimal value
        Console.Write("Hexadecimal value: ");
        Console.WriteLine(value1.ToString("X"));
    }
}
```

**Output:**

```cs
double-precision floating point: 1

64-bit signed integer: 4607182418800017408

Hexadecimal value: 3FF0000000000000

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . double toint 64 bit？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.doubletoint64bits?view=netframework-4.7.2)