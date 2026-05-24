# C# | Convert.ToInt64(String, IFormatProvider) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-toint64string-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-toint64string-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的 64 位有符号整数。

## 语法

```cs
public static long ToInt64 (string value, IFormatProvider provider);
```

## 参数

*   `value`：是包含要转换的数字的字符串。
*   `provider`：它是一个提供区域性特定格式信息的对象。

## 返回值

该方法返回一个十进制数，它相当于 `value` 中的数字，如果 `value` 为 `null`，则返回 0（零）。

## 异常

*   `FormatException`：如果 `value` 不是由后跟数字序列（0 到 9）的可选符号组成。
*   `OverflowException`：如果 `value` 代表小于 `MinValue` 或大于 `MaxValue` 的数字。

以下程序说明了 `Convert.ToInt64(String, IFormatProvider)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// Convert.ToInt64() Method
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
            Console.Write("Converted long value"
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

        // converting string to specified long
        long val = Convert.ToInt64(s, cultures);

        // display the converted long value
        Console.Write(" {0}, ", val);
    }
}
```

**Output:**

```cs
Converted long value from a specified string  12345,  12345,  -12345,
```

### 例 2：为 `FormatException`

```cs
// C# program to demonstrate the
// Convert.ToInt64() Method
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
            Console.Write("Converted long value"
                        + " of specified strings: ");

            for (int j = 0; j < values.Length; j++) 
            {
                get(values[j], cultures);
            }

            Console.WriteLine("\n");
            string s = "123 456, 789";

            Console.WriteLine("format of s is invalid ");

            // converting string to specified char
            long val = Convert.ToInt64(s, cultures);

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
        // specified long value
        long val = Convert.ToInt64(s, cultures);

        // display the converted
        // decimal value
        Console.Write(" {0}, ", val);
    }
}
```

**Output:**

```cs
Converted long value of specified strings:  12345,  12345,  -12345,

format of s is invalid 
Exception Thrown: System.FormatException
```

### 例 3：适用于 `OverflowException`

```cs
// C# program to demonstrate the
// Convert.ToInt64() Method
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
            Console.Write("Converted long value "
                     + "of specified strings: ");

            for (int j = 0; j < values.Length; j++)
            {
                get(values[j], cultures);
            }

            Console.WriteLine("\n");
            string s = "-7922816251426433759354395033500000";

            Console.WriteLine("s is less than the MinValue");

            // converting string to specified long
            long val = Convert.ToInt64(s, cultures);

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
        // specified long value
        long val = Convert.ToInt64(s, cultures);

        // display the converted long value
        Console.Write(" {0}, ", val);
    }
}
```

**Output:**

```cs
Converted long value of specified strings:  12345,  12345,  -12345,

s is less than the MinValue
Exception Thrown: System.OverflowException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.toint64?view=netframework-4.7.2#System_Convert_ToInt64_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.toint64?view=netframework-4.7.2#System_Convert_ToInt64_System_String_System_IFormatProvider_)