# C# | Convert。双(字符串，表单提供者)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-convert-to doublesting-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-todoublestring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的双精度浮点数。

**语法:**

> 公共静态 double ToDouble(字符串值，IFormatProvider 提供程序)；

**参数:**

*   **值:**是包含要转换的数字的字符串。
*   **提供程序:**它是一个提供区域性特定格式信息的对象。

**返回值:**该方法返回一个双精度浮点数，相当于*值*中的数字，如果*值*为*空值*，则返回 0(零)。

**异常:**

*   **格式异常:**如果*值*不是有效格式的数字。
*   **overoverowexception:**如果*值*代表小于*最小值*或大于*最大值*的数字。

以下程序说明了**转换的使用。ToDouble(字符串，表单提供者)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// Convert.ToDouble() Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{
    try {

        // Create a NumberFormatInfo object 
        // and set some of its properties.
        NumberFormatInfo provider = new NumberFormatInfo();
        provider.NumberDecimalSeparator = ", ";
        provider.NumberGroupSeparator = ".";
        provider.NumberGroupSizes = new int[] { 3 };

        // declaring and initializing String array
        string[] values = {"123456789", "12345.6789",
                                      "12345, 6789"};

        // calling get() Method
        Console.Write("Converted decimal value "
                         + "of specified strings: ");

        for (int j = 0; j < values.Length; j++) 
        {
            get(values[j], provider);
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
      NumberFormatInfo provider)
{

    // converting string to specified char
    double val = Convert.ToDouble(s, provider);

    // display the converted char value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted decimal value of specified strings:  123456789,  123456789,  12345.6789,

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// Convert.ToDouble() Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{
    try {

        // Create a NumberFormatInfo object 
        // and set some of its properties.
        NumberFormatInfo provider = new NumberFormatInfo();
        provider.NumberDecimalSeparator = ", ";
        provider.NumberGroupSeparator = ".";
        provider.NumberGroupSizes = new int[] { 3 };

        // declaring and initializing String array
        string[] values = {"123456789", "12345.6789",
                                      "12345, 6789"};

        // calling get() Method
        Console.Write("Converted double value"
                 + " of specified strings: ");

        for (int j = 0; j < values.Length; j++)
        {

            get(values[j], provider);
        }

        Console.WriteLine("\n");
        string s = "123 456, 789";

        Console.WriteLine("format of s is invalid ");

        // converting string to specified char
        double val = Convert.ToDouble(s, provider);

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
      NumberFormatInfo provider)
{

    // converting string to specified char
    double val = Convert.ToDouble(s, provider);

    // display the converted char value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted double value of specified strings:  123456789,  123456789,  12345.6789, 

format of s is invalid 
Exception Thrown: System.FormatException

```

**例 3:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Convert.ToDouble() Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{
    try {

        // Create a NumberFormatInfo object
        // and set some of its properties.
        NumberFormatInfo provider = new NumberFormatInfo();
        provider.NumberDecimalSeparator = ", ";
        provider.NumberGroupSeparator = ".";
        provider.NumberGroupSizes = new int[] { 3 };

        // declaring and initializing String array
        string[] values = { "123456789", "12345.6789",
                                      "12345, 6789" };

        // calling get() Method
        Console.Write("Converted decimal value "
                    + "of specified strings: ");

        for (int j = 0; j < values.Length; j++)
        {

            get(values[j], provider);
        }

        Console.WriteLine("\n");
        string s = "-7922816251426433759354395033500000";

        Console.WriteLine("s is less than the MaxValue");

        // converting string to specified char
        decimal val = Convert.ToDecimal(s, provider);

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
      NumberFormatInfo provider)
{

    // converting string to specified char
    double val = Convert.ToDouble(s, provider);

    // display the converted char value
    Console.Write(" {0}, ", val);
}
}
```

**Output:**

```cs
Converted decimal value of specified strings:  123456789,  123456789,  12345.6789, 

s is less than the MaxValue
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . to double？view = net framework-4 . 7 . 2 # System _ Convert _ to double _ System _ String _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.todouble?view=netframework-4.7.2# System_Convert_ToDouble_System_String_System_IFormatProvider_)