# BitConverter.DoubleToInt64Bits(Double) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-bitconverter-doubletoint64bits-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-doubletoint64bits-method/)

`BitConverter.DoubleToInt64Bits(Double)` 方法用于将指定的双精度浮点数转换为 64 位有符号整数。

## 语法

```cs
public static long DoubleToInt64Bits (double value);
```

这里 `value` 是要转换的数字。

## 返回值

该方法返回一个 64 位有符号整数，其值相当于 `value`。

以下程序说明了 `BitConverter.DoubleToInt64Bits(Double)` 方法的使用：

### 示例 1

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

**输出：**

```cs
double-precision floating point: 1.23456789012346

64-bit signed integer: 4608238818662570490
```

### 示例 2

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

**输出：**

```cs
double-precision floating point: 1

64-bit signed integer: 4607182418800017408

Hexadecimal value: 3FF0000000000000
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.doubletoint64bits?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.doubletoint64bits?view=netframework-4.7.2)