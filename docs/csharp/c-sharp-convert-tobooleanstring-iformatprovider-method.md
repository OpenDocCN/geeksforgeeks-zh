# C# | Convert。工具(字符串、表单提供者)方法

> 原文:[https://www . geesforgeks . org/c-sharp-convert-to pool ean string-iformat provider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tobooleanstring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将逻辑值的指定字符串表示形式转换为其布尔等效形式。
**语法:**

```cs
public static bool ToBoolean (string value, IFormatProvider provider);
```

**参数:**

*   **值:**是包含 *TrueString* 或 *FalseString* 值的字符串。
*   **提供程序:**它是一个提供区域性特定格式信息的对象。此参数被忽略。

**返回值:**如果值等于 *TrueString* ，则该方法返回 *true* ，如果值等于 *FalseString* 或 *null* ，则返回 *false* 。
**异常:**如果*值*不等于*真弦*或*假弦*，此方法将抛出*格式异常*。
以下程序说明了**转换的使用。ToBoolean(String，IFormatProvider)** 方法:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Convert.ToBoolean() Method
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
        String[] values = { null, "true",
                    "False", " false " };

        // calling get() Method
        Console.WriteLine("Converted bool value "+
                        "of specified strings: ");

        for (int j = 0; j < values.Length; j++) {
            get(values[j], cultures);
        }
    }

    catch (FormatException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining get() method
public static void get(string s, CultureInfo cultures)
{

    // converting string to specified bool
    bool val = Convert.ToBoolean(s, cultures);

    // display the converted string
    Console.Write(" {0}, ", val);
}
}
```

**Output:** 

```cs
Converted bool value of specified strings: 
 False,  True,  False,  False,
```

**例 2:** 为*格式异常*

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Convert.ToBoolean() Method
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
        String[] values = { null, "true",
                "False", " false ", "" };

        // calling get() Method
        Console.WriteLine("Converted bool value"+
                      " of specified strings: ");

        for (int j = 0; j < values.Length; j++) {
            get(values[j], cultures);
        }
    }

    catch (FormatException e) {
        Console.WriteLine("\n");
        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining get() method
public static void get(string s, CultureInfo cultures)
{

    // converting string to specified bool
    bool val = Convert.ToBoolean(s, cultures);

    // display the converted string
    Console.Write(" {0}, ", val);
}
}
```

**Output:** 

```cs
Converted bool value of specified strings: 
 False,  True,  False,  False, 

Exception Thrown: System.FormatException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . to boolean？view = net framework-4 . 7 . 2 # System _ Convert _ to boolean _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.toboolean?view=netframework-4.7.2# System_Convert_ToBoolean_System_String_System_IFormatProvider_)