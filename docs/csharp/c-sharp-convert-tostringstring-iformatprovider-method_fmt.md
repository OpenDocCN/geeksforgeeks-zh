# C# `Convert.ToString(String, IFormatProvider)` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-tostringstring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tostringstring-iformatprovider-method/)

此方法用于返回指定的字符串实例，并且不执行实际转换。

## 语法

```cs
public static string ToString (String, IFormatProvider);
```

## 参数

*   `value`：返回的字符串。
*   `provider`：它是一个提供区域性特定格式信息的对象。此参数被忽略。

## 返回值

此方法返回值不变返回。

下面的程序说明了 `Convert.ToString()` 方法的使用。

## 示例 1

```cs
// C# program to demonstrate the
// Convert.ToString() Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of CultureInfo
            CultureInfo cultures =
              new CultureInfo("en-US");

// declaring and initializing String array
            string[] values = {"amar", "akbar",
                                "anthony"};

// calling get() Method
            Console.Write("Converted string value"
                  + " from a specified string: ");

for (int j = 0; j < values.Length; j++)
            {
                get(values[j], cultures);
            }
        }

catch (FormatException e)
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

catch (OverflowException e)
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

// Defining get() method
    public static void get(string s,
               CultureInfo cultures)
    {

// converting string to specified string
        string val = Convert.ToString(s, cultures);

// display the converted string value
        Console.Write(" {0} ", val);
    }
}
```

**Output:**

```cs
Converted string value from a specified string:  amar  akbar  anthony
```

## 示例 2

```cs
// C# program to demonstrate the
// Convert.ToString() Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        // creating object of CultureInfo
        CultureInfo cultures =
          new CultureInfo("en-US");

// declaring and initializing a String array
        string value = "The Accidental Prime Minister";

// calling get() Method
        Console.Write("Converted String: ");

// converting string to specified string
        string val = Convert.ToString(value, cultures);

// display the converted string value
        Console.Write("{0}", val);
    }
}
```

**Output:**

```cs
Converted String: The Accidental Prime Minister
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.tostring?view=netframework-4.7.2#System_Convert_ToString_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tostring?view=netframework-4.7.2#System_Convert_ToString_System_String_System_IFormatProvider_)