# C# | Convert。ToSByte(字符串，表单提供者)方法

> 原文:[https://www . geesforgeks . org/c-sharp-convert-tosbytestring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tosbytestring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的 8 位有符号整数。

**语法:**

```cs
public static sbyte ToSByte (string value, IFormatProvider provider);

```

**参数:**

*   **值**:包含要转换的数字的字符串。
*   **提供程序**:它是一个提供区域性特定格式信息的对象。

**返回值:**该方法返回一个 8 位有符号整数，相当于*值*。

**异常:**

*   **参数空异常:**如果*值*为空。
*   **格式异常:**如果*值*不是由后跟数字序列(0 到 9)的可选符号组成。
*   **overoverowexception:**如果*值*代表小于*最小值*或大于*最大值*的数字。

以下程序说明了**转换的使用。ToSByte(字符串，表单提供者)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// Convert.ToSByte() Method
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
        string[] values = {"123", "+123", "-123"};

        // calling get() Method
        Console.Write("Converted sbyte value"
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

    // converting string to specified sbyte
    sbyte val = Convert.ToSByte(s, cultures);

    // display the converted sbyte value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted sbyte value from a specified string:  123,  123,  -123,

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// Convert.ToSByte() Method
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
        string[] values = {"123", "+123", "-123"};

        // calling get() Method
        Console.Write("Converted sbyte value"
                + " of specified strings: ");

        for (int j = 0; j < values.Length; j++)
        {
            get(values[j], cultures);
        }

        Console.WriteLine("\n");
        string s = "123 456, 789";

        Console.WriteLine("format of s is invalid");

        // converting string to specified sbyte
        sbyte val = Convert.ToSByte(s, cultures);

        // display the converted ToSByte value
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
    // specified sbyte value
    sbyte val = Convert.ToSByte(s, cultures);

    // display the converted
    // sbyte value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted sbyte value of specified strings:  123,  123,  -123, 

format of s is invalid
Exception Thrown: System.FormatException

```

**例 3:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Convert.ToSByte() Method
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
        string[] values = {"123", "+123", "-123"};

        // calling get() Method
        Console.Write("Converted sbyte value "
                  + "of specified strings: ");

        for (int j = 0; j < values.Length; j++) 
        {
            get(values[j], cultures);
        }

        Console.WriteLine("\n");
        string s = "-7922816251426433759354395033500000";

        Console.WriteLine("s is less than the MinValue");

        // converting string to specified sbyte
        sbyte val = Convert.ToSByte(s, cultures);

        // display the converted sbyte value
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
    // specified sbyte value
    sbyte val = Convert.ToSByte(s, cultures);

    // display the converted sbyte value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted sbyte value of specified strings:  123,  123,  -123, 

s is less than the MinValue
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . tosbyte？view = net framework-4 . 7 . 2 # System _ Convert _ ToSByte _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tosbyte?view=netframework-4.7.2# System_Convert_ToSByte_System_String_System_IFormatProvider_)