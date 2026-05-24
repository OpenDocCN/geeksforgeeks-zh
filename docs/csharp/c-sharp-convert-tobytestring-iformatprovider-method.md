# C# | Convert。ToByte(字符串，表单提供者)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-convert-to bytestring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tobytestring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的 8 位无符号整数。
**语法:**

```cs
public static byte ToByte (string value, IFormatProvider provider);
```

**参数:**

*   **值:**是包含要转换的数字的字符串。
*   **提供程序:**它是一个提供区域性特定格式信息的对象。

**返回值:**该方法返回一个 8 位无符号整数，相当于*值*，如果*值*为*空值*，则返回零。
**例外:**

*   **格式异常:**如果值不是由可选符号后跟一系列数字(0 到 9)组成。
*   **OverflowException:** 如果该值代表小于*最小值*或大于*最大值*的数字。

以下程序说明了**转换的使用。ToByte(String，IFormatProvider)** 方法:
T3】例 1:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Convert.ToByte() Method
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
        string[] values = { "234", "+234", "240",
                           "255", "140", "120" };

        // calling get() Method
        Console.WriteLine("Converted bool value "+
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
public static void get(string s, CultureInfo cultures)
{

    // converting string to specified bool
    byte val = Convert.ToByte(s, cultures);

    // display the converted string
    Console.Write(" {0}, ", val);
}
}
```

**Output:** 

```cs
Converted bool value of specified strings: 
 234,  234,  240,  255,  140,  120,
```