# C# Convert.ToDecimal(String, IFormatProvider) 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-convert-todecimalstring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-todecimalstring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的十进制数。

**语法:**

```cs
public static decimal ToDecimal (string value, IFormatProvider provider);
```

**参数:**

*   `value`: 是包含要转换的数字的字符串。
*   `provider`: 它是一个提供区域性特定格式信息的对象。

**返回值:** 该方法返回一个十进制数，该十进制数相当于数值中的数字，如果数值为空，则返回 0（零）。

**异常:**

*   `FormatException`: 如果 `value` 不是有效格式的数字。
*   `OverflowException`: 如果 `value` 代表小于最小值或大于最大值的数字。

以下程序说明了 `Convert.ToDecimal()` 方法的使用:

### 示例 1

```cs
// C# program to demonstrate the
// Convert.ToDecimal() Method
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
            string[] values = {"123456789", "12345.6789",
                               "123,456,789.0123"};

            // calling get() Method
            Console.WriteLine("Converted decimal value "+
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
        decimal val = Convert.ToDecimal(s, cultures);

        // display the converted char value
        Console.Write(" {0}, ", val);
    }
}
```

**输出:**

```cs
Converted decimal value of specified strings: 
 123456789,  12345.6789,  123456789.0123, 
```

### 示例 2: 用于 `FormatException`

```cs
// C# program to demonstrate the
// Convert.ToDecimal() Method
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
            string[] values = {"123456789", "12345.6789",
                               "123,456,789.0123"};

            // calling get() Method
            Console.WriteLine("Converted decimal value"+
                              " of specified strings: ");

            for (int j = 0; j < values.Length; j++) {

                get(values[j], cultures);
            }

            Console.WriteLine("\n");
            string s = "123 456, 789";

            Console.WriteLine("format of s is invalid ");

            // converting string to specified char
            decimal val = Convert.ToDecimal(s, cultures);

            // display the converted char value
            Console.Write(" {0}, ", val);
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (OverflowException e) {

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
        decimal val = Convert.ToDecimal(s, cultures);

        // display the converted decimal value
        Console.Write(" {0}, ", val);
    }
}
```

**输出:**

```cs
Converted decimal value of specified strings: 
 123456789,  12345.6789,  123456789.0123,

format of s is invalid 
Exception Thrown: System.FormatException
```

### 示例 3: 适用于 `OverflowException`

```cs
// C# program to demonstrate the
// Convert.ToDecimal() Method
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
            string[] values = {"123456789", "12345.6789",
                               "123,456,789.0123"};

            // calling get() Method
            Console.WriteLine("Converted decimal value "+
                               "of specified strings: ");

            for (int j = 0; j < values.Length; j++) {

                get(values[j], cultures);
            }

            Console.WriteLine("\n");
            string s = "-7922816251426433759354395033500000";

            Console.WriteLine("s is less than the MinValue");

            // converting string to specified char
            decimal val = Convert.ToDecimal(s, cultures);

            // display the converted char value
            Console.Write(" {0}, ", val);
        }
        catch (FormatException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (OverflowException e) {
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
        decimal val = Convert.ToDecimal(s, cultures);

        // display the converted decimal value
        Console.Write(" {0}, ", val);
    }
}
```

**输出:**

```cs
Converted decimal value of specified strings: 
 123456789,  12345.6789,  123456789.0123,

s is less than the MinValue
Exception Thrown: System.OverflowException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.todecimal?view=netframework-4.7.2#System_Convert_ToDecimal_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.todecimal?view=netframework-4.7.2#System_Convert_ToDecimal_System_String_System_IFormatProvider_)