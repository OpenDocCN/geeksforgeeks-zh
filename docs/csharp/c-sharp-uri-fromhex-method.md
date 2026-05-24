# C# | Uri。FromHex()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-uri-fromhex-method/](https://www.geeksforgeeks.org/c-sharp-uri-fromhex-method/)

**乌利。FromHex(Char)方法**用于获取一个十六进制数字的十进制值。

> **语法:** public static int FromHex(字符数字)；
> 这里取十六进制数字(0-9，a-f，A-F)进行转换。
> 
> **返回值:**该方法返回一个 Int32 值，该值包含一个从 0 到 15 的数字，对应于指定的十六进制数字。
> 
> **异常:**如果数字不是有效的十六进制数字(0-9，a-f，A-F)，此方法抛出**参数异常**。

下面的程序说明了 *Uri 的使用。FromHex(Char)* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.FromHex(Char) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing Char value
        char value = 'A';

        // Gets the decimal value 
        // of a hexadecimal digit.
        // using FromHex() method
        int dec = Uri.FromHex(value);

        // Displaying the result
        Console.WriteLine("Converted int value : {0}", dec);
    }
}
```

**Output:**

```cs
Converted int value : 10

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// Uri.FromHex(Char) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing
            // Char value
            char value = '.';

            // Gets the decimal value 
            // of a hexadecimal digit.
            // using FromHex() method
            int dec = Uri.FromHex(value);

            // Displaying the result
            Console.WriteLine("Converted int value : {0}", dec);
        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("Digit should be a valid "+
                   "Hexadecimal digit (0-9, a-f, A-F).");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Digit should be a valid Hexadecimal digit (0-9, a-f, A-F).
Exception Thrown: System.ArgumentException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . from hex？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.fromhex?view=netstandard-2.1)