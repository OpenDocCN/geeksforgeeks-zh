# C# | Char。ConvertFromUtf32(Int32)方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-convertfromutf32 int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-convertfromutf32int32-method/)

此方法用于将指定的 Unicode 代码点转换为 UTF-16 编码的字符串。
**语法:**

```cs
public static string ConvertFromUtf32 (int utf32);
```

这里， *utf32* 是 21 位 Unicode 码位。
**返回值:**该方法返回一个字符串，该字符串由一个 Char 对象或一对替代 Char 对象组成，相当于 *utf32* 参数指定的代码点。
**异常:**如果 *utf32* 不是从 *U+0* 到 *U+10FFFF* 的有效 21 位 Unicode 码点，则该方法返回**argumentout of range Exception**，不包括从 *U+D800* 到 *U+DFFF* 的代理项对范围。
下面的程序说明了 **Char 的使用。convertfrommutf32(Int32)**方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Char.ConvertFromUtf32(Int32)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // declaring and initializing
            // int variablewith 21 bit
            // unicode
            int utf = 0x0042;

            // getting the value
            // using ConvertFromUtf32()
            string value = Char.ConvertFromUtf32(utf);

            // Display the value
            Console.WriteLine("value is {0}", value);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
value is B
```

**例 2:** 为*argumentout of range exception*

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Char.ConvertFromUtf32(Int32)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // declaring and initializing
            // int variable with 21 bit
            // unicode
            int utf = 0x11FFFF;

            // getting the value
            // using ConvertFromUtf32()
            Console.WriteLine("0x11FFFF is excedding the limit");
            string value = Char.ConvertFromUtf32(utf);

            // Display the value
            Console.WriteLine("value is {0}", value);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
0x11FFFF is excedding the limit
Exception Thrown: System.ArgumentOutOfRangeException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . convertfromutf32？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.convertfromutf32?view=netframework-4.7.2)