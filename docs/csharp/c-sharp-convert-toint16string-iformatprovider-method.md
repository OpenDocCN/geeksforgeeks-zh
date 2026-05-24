# C# | Convert。ToInt16(字符串，表单提供者)方法

> 原文:[https://www . geesforgeks . org/c-sharp-convert-to t16 string-iformat provider-method/](https://www.geeksforgeeks.org/c-sharp-convert-toint16string-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的 16 位有符号整数。

**语法:**

> public static short ToInt16(字符串值，IFormatProvider 提供程序)；

**参数:**

*   **值:**是包含要转换的数字的字符串。
*   **提供程序:**它是一个提供区域性特定格式信息的对象。

**返回值:**该方法返回一个十进制数，该十进制数相当于数值中的数字，如果数值为空，则返回 0(零)。

**异常:**

*   **格式异常**:如果*值*不是由可选符号后跟数字序列(0 到 9)组成。
*   **overoverowexception**:如果值代表小于*最小值*或大于最大值的数字。

以下程序说明了**转换的使用。至特定(字符串、表单提供者)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// Convert.ToInt16() Method
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
        string[] values = {"12345", "+12345", 
                                   "-12345"};

        // calling get() Method
        Console.Write("Converted short value"+
                    " from a specified string ");

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

    // converting string to specified short
    short val = Convert.ToInt16(s, cultures);

    // display the converted char value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted short value from a specified string  12345,  12345,  -12345,

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// Convert.ToInt16() Method
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
        string[] values = {"12345", "+12345", 
                                   "-12345"};

        // calling get() Method
        Console.Write("Converted short value"+
                       " of specified strings: ");

        for (int j = 0; j < values.Length; j++) 
        {
            get(values[j], cultures);
        }

        Console.WriteLine("\n");
        string s = "123 456, 789";

        Console.WriteLine("format of s is invalid ");

        // converting string to specified char
        short val = Convert.ToInt16(s, cultures);

        // display the converted char value
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
    // specified short value
    short val = Convert.ToInt16(s, cultures);

    // display the converted 
    // decimal value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted short value of specified strings:  12345,  12345,  -12345, 

format of s is invalid 
Exception Thrown: System.FormatException

```

**例 3:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Convert.ToInt16() Method
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
        string[] values = { "12345", "+12345", 
                                   "-12345" };

        // calling get() Method
        Console.Write("Converted short value "+
                     "of specified strings: ");

        for (int j = 0; j < values.Length; j++)
        {
            get(values[j], cultures);
        }

        Console.WriteLine("\n");
        string s = "-7922816251426433759354395033500000";

        Console.WriteLine("s is less than the MinValue");

        // converting string to specified short
        short val = Convert.ToInt16(s, cultures);

        // display the converted char value
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
    // specified decimal value
    short val = Convert.ToInt16(s, cultures);

    // display the converted decimal value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted short value of specified strings:  12345,  12345,  -12345, 

s is less than the MinValue
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . to int 16？view = net framework-4 . 7 . 2 # System _ Convert _ toint 16 _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.toint16?view=netframework-4.7.2# System_Convert_ToInt16_System_String_System_IFormatProvider_)