# C# | Char。转换输出 32(字符串，Int32)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-converttoft 32 string-int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-converttoutf32string-int32-method/)

此方法用于将字符串中指定位置的 UTF-16 编码字符或代理项对的值转换为 Unicode 代码点。

**语法:**

```cs
public static int ConvertToUtf32 (string s, int index);
```

**参数:**

> **s:** 包含字符或代理项对的字符串。
> **索引:**字符或代理对在 s 中的索引位置。

**返回值:**该方法返回由 ***s*** 参数中由 ***索引*** 参数指定的位置的字符或代理对表示的 21 位 Unicode 码点。

**异常:**

*   **ArgumentNullException:** 如果 s 为空。
*   **argumentout of range exception:**如果*指数*不在*的*之内。
*   **参数异常:**如果*指数*不是 *s* 内的位置。
*   **ArgumentException:** 如果指定的索引位置包含代理项对，并且该对中的第一个字符不是有效的高代理项，或者该对中的第二个字符不是有效的低代理项。

以下程序说明了**字符的使用。转换输出 32(字符串，Int32)** 方法:

**例 1:**

```cs
// C# program to demonstrate
// Char.ConvertToUtf32(String, Int32)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{
    try {

        // declaring and initializing int 
        // variable with 21 bit unicode
        int utf = 0xF42;

        // getting the value
        // using ConvertFromUtf32()
        string value = Char.ConvertFromUtf32(utf);

        // getting unicode point
        // using ConvertToUtf32() method
        int val = Char.ConvertToUtf32(value, 0);

        // Display the value
        Console.WriteLine("value is 0x{0:X}", val);
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
value is 0xF42

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate
// Char.ConvertToUtf32(String, Int32)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{
    try {

        // declaring and initializing int 
        // variable with 21 bit unicode
        int utf = 0x42F;

        // getting the value
        // using ConvertFromUtf32()
        string value = Char.ConvertFromUtf32(utf);

        // getting unicode point
        // using ConvertToUtf32() method
        Console.WriteLine("index is not a position within s.");
        int val = Char.ConvertToUtf32(value, 0xDFFF);

        // Display the value
        Console.WriteLine("value is 0x{0:X}", val);
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
index is not a position within s.
Exception Thrown: System.ArgumentOutOfRangeException

```

**例 3:** 为***ArgumentNullException***

```cs
// C# program to demonstrate
// Char.ConvertToUtf32(String, Int32)
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
            // unicode int utf = 0x42F;

            // getting the value
            // using ConvertFromUtf32()
            string value = null;

            // getting unicode point
            // using ConvertToUtf32() method
            Console.WriteLine("string value is null");
            int val = Char.ConvertToUtf32(value, 0);

            // Display the value
            Console.WriteLine("value is 0x{0:X}", val);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
string value is null
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . converttoft 32？view = net framework-4 . 7 . 2 # System _ Char _ converttoft 32 _ System _ String _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.char.converttoutf32?view=netframework-4.7.2# System_Char_ConvertToUtf32_System_String_System_Int32_)