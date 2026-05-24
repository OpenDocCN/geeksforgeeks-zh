# C# | BitConverter。Int64BitsToDouble()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-int 64 bitstodouble-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-int64bitstodouble-method/)

**BitConverter。Int64BitsToDouble(Int64)方法**用于将指定的 64 位有符号整数转换为双精度浮点数。

**语法:**

```cs
public static double Int64BitsToDouble (long value);
```

**参数:**该方法以 64 位有符号整数**值**为参数。

**返回值:**该方法返回一个双精度浮点数，其值相当于*值*。

以下程序说明了**位转换器的使用。Int64BitsToDouble(Int64)** 方法:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.Int64BitsToDouble(Int64)
// Method
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing 
        // double value
        long value = 214748364;

        // Display the double value
        Console.Write("64-bit signed integer: ");
        Console.WriteLine("{0}", value);
        Console.WriteLine();

        // Converting double to long value
        // using BitConverter.DoubleToInt64Bits()
        // Method
        double value1 = BitConverter.Int64BitsToDouble(value);

        // Display the 64-bit signed integer.
        Console.Write("double-precision floating point number: ");
        Console.WriteLine("{0}", value1);
    }
}
```

**Output:**

```cs
64-bit signed integer: 214748364

double-precision floating point number: 1.06099789153011E-315

```

**例 2:**

```cs
// C# program to demonstrate
// BitConverter.Int64BitsToDouble(Int64)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing
        // double value
        long value = 1;

        // Display the double value
        Console.Write("64-bit signed integer: ");
        Console.WriteLine("{0}", value);
        Console.WriteLine();

        // Converting double to long value
        // using BitConverter.DoubleToInt64Bits()
        // Method
        double value1 = BitConverter.Int64BitsToDouble(value);

        // Display the 64-bit signed integer.
        Console.Write("double-precision floating point number: ");
        Console.WriteLine("{0}", value1);
    }
}
```

**Output:**

```cs
64-bit signed integer: 1

double-precision floating point number: 4.94065645841247E-324

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . int 64 bitstodouble？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.int64bitstodouble?view=netframework-4.7.2)