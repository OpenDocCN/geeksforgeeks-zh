# C# | Convert。ToSingle(字符串，表单提供者)方法

> 原文:[https://www . geesforgeks . org/c-sharp-convert-to singlestring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tosinglestring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的单精度浮点数。
**语法:**

```cs
public static float ToSingle (string value, IFormatProvider provider);
```

**参数:**

*   **值:**是包含要转换的数字的字符串。
*   **提供程序:**它是一个提供区域性特定格式信息的对象。

**返回值:**该方法返回一个单精度浮点数，该浮点数与值中的数字相等，如果值为空，则返回 0(零)。
T3】例外:

*   **格式异常:**如果*值*不是由后跟数字序列(0 到 9)的可选符号组成。
*   **overoverowexception:**如果*值*代表小于*最小值*或大于*最大值*的数字。

以下程序说明了**转换的使用。**方法:
T3】例 1:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Convert.ToSingle() Method
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
        string[] values = {"123.45", "+12.345",
                                    "-1234.5"};

        // calling get() Method
        Console.Write("Converted float value"
             + " from a specified string ");

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

    // converting string to specified float
    float val = Convert.ToSingle(s, cultures);

    // display the converted float value
    Console.Write(" {0}, ", val);
}
}
```

**Output**

```cs
Converted float value from a specified string  123.45,  12.345,  -1234.5, 
```

**例 2:** 为*格式异常*

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Convert.ToSingle() Method
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
        string[] values = {"12.345", "+1234.5",
                                    "-123.45"};

        // calling get() Method
        Console.Write("Converted float value"
                + " of specified strings: ");

        for (int j = 0; j < values.Length; j++)
        {
            get(values[j], cultures);
        }

        Console.WriteLine("\n");
        string s = "123 456, 789";

        Console.WriteLine("format of s is invalid ");

        // converting string to specified float
        float val = Convert.ToSingle(s, cultures);

        // display the converted float value
        Console.Write(" {0}, ", val);
    }

    catch (FormatException e)
    {
        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }

    catch (OverflowException e)
    {
        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining get() method
public static void get(string s,
           CultureInfo cultures)
{

    // converting string to
    // specified float value
    float val = Convert.ToSingle(s, cultures);

    // display the converted
    // float value
    Console.Write(" {0}, ", val);
}
}
```

**Output:** 

```cs
Converted float value of specified strings:  12.345,  1234.5,  -123.45, 

format of s is invalid 
Exception Thrown: System.FormatException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . to single？view = net framework-4 . 7 . 2 # System _ Convert _ to single _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tosingle?view=netframework-4.7.2# System_Convert_ToSingle_System_String_System_IFormatProvider_)