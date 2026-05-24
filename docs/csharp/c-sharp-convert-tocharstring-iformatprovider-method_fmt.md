# C# Convert.ToChar(String, IFormatProvider) Method

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-tocharstring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tocharstring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将指定对象的值转换为其等效的 Unicode 字符。

## 语法

```cs
public static char ToChar (object value, IFormatProvider provider);
```

## 参数

*   `value`：是长度为 1 或为空的字符串。
*   `provider`：它是一个提供区域性特定格式信息的对象。

## 返回值

该方法返回一个 Unicode 字符，该字符相当于 `value` 中的第一个也是唯一一个字符。

## 异常

*   `ArgumentNullException`：如果 `value` 为空。
*   `FormatException`：如果 `value` 的长度不是 1。

以下程序说明了 `Convert.ToChar()` 方法的使用：

## 示例 1

```cs
// C# program to demonstrate the
// Convert.ToChar() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = new CultureInfo("en-US");

            // declaring and initializing
            // String array
            string[] values = {"A", "B", "a", 
                              "b", "x", "z"};

            // calling get() Method
            Console.WriteLine("Converted char value "+
                            "of specified strings: ");

            for (int j = 0; j < values.Length; j++) {

                get(values[j], cultures);
            }
        }

        catch (FormatException e) {

            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (OverflowException e) {

            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string s, 
               CultureInfo cultures)
    {

        // converting string to specified char
        char val = Convert.ToChar(s, cultures);

        // display the converted char value
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**

```cs
Converted char value of specified strings: 
 A,  B,  a,  b,  x,  z,
```

## 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Convert.ToChar() Method
using System;
using System.Globalization;
class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = new CultureInfo("en-US");

            // declaring and initializing String array
            string[] values = {"A", "B", "a",
                              "b", "x", "z"};

            // calling get() Method
            Console.WriteLine("Converted char value "+
                            "of specified strings: ");

            for (int j = 0; j < values.Length; j++) {
                get(values[j], cultures);
            }
            Console.WriteLine("\n");
            string s = null;

            Console.WriteLine("s is null ");

            // converting string to specified char
            char val = Convert.ToChar(s, cultures);

            // display the converted char value
            Console.Write(" {0}, ", val);
        }

        catch (FormatException e) {

            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string s, CultureInfo cultures)
    {

        // converting string to specified char
        char val = Convert.ToChar(s, cultures);

        // display the converted char value
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**

```cs
Converted char value of specified strings: 
 A,  B,  a,  b,  x,  z,

s is null 
Exception Thrown: System.ArgumentNullException
```

## 示例 3：为 `FormatException`

```cs
// C# program to demonstrate the
// Convert.ToChar() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // creating object of CultureInfo
            CultureInfo cultures = new CultureInfo("en-US");

            // declaring and initializing String array
            string value1 = "x";
            string value2 = "xyz";

            get(value1, cultures);

            Console.WriteLine("\nlength of value2 is not 1");
            get(value2, cultures);
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string s, 
               CultureInfo cultures)
    {
        // converting string to specified char
        char val = Convert.ToChar(s, cultures);

        // display the converted char value
        Console.WriteLine("string to char value : {0} ", val);
    }
}
```

**输出：**

```cs
string to char value : x

length of value2 is not 1
Exception Thrown: System.FormatException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.tochar?view=netframework-4.7.2#System_Convert_ToChar_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tochar?view=netframework-4.7.2#System_Convert_ToChar_System_String_System_IFormatProvider_)