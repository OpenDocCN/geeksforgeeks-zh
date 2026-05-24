# C# | Convert。ToString(字符串，表单提供者)方法

> 原文:[https://www . geesforgeks . org/c-sharp-convert-tostringstring-iformat provider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tostringstring-iformatprovider-method/)

此方法用于返回指定的字符串实例，并且不执行实际转换。
**语法:**

```cs
public static string ToString (String, IFormatProvider);
```

**参数:**

*   **值**:返回的字符串。
*   **提供程序**:它是一个提供区域性特定格式信息的对象。此参数被忽略。

**返回值:**此方法返回值不变返回。
下面的程序说明了**转换的使用。**方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

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

**例 2:**

## c sharp . c sharp . c sharp . c sharp

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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . tostring？view = net framework-4 . 7 . 2 # System _ Convert _ ToString _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tostring?view=netframework-4.7.2# System_Convert_ToString_System_String_System_IFormatProvider_)