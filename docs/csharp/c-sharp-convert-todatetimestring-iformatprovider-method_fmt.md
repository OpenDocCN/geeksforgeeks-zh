# C# Convert.ToDateTime(String, IFormatProvider) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-todatetimestring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-todatetimestring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将数字的指定字符串表示形式转换为等效的日期和时间。

## 语法

```cs
public static DateTime ToDateTime (string value, IFormatProvider provider);
```

## 参数

*   `value`：包含要转换的日期和时间的字符串。
*   `provider`：提供区域性特定格式信息的对象。

## 返回值

此方法返回 `value` 的日期时间等价物，如果 `value` 为 `null`，则返回 `DBNull.Value` 的日期时间等价物。

## 异常

如果 `value` 不是格式正确的日期和时间字符串，此方法将给出 `FormatException`。

以下程序说明了 `Convert.ToDateTime(String, IFormatProvider)` 方法的使用。

### 示例 1

```cs
// C# program to demonstrate the
// Convert.ToDateTime() Method
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
            string[] values = {"01/02/09", "2009/02/03",
                "01/2009/03", "01/02/2009", "01/02/23"};

            // calling get() Method
            Console.WriteLine("Converted string value"+
                           " to specified DateTime: ");

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
    public static void get(string s,
               CultureInfo cultures)
    {

        // converting string to specified bool
        DateTime val = Convert.ToDateTime(s, cultures);

        // display the converted string
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**
Converted string value to specified DateTime: 01/02/2009 00:00:00, 02/03/2009 00:00:00, 01/03/2009 00:00:00, 01/02/2009 00:00:00, 01/02/2023 00:00:00,

### 示例 2：`FormatException`

```cs
// C# program to demonstrate the
// Convert.ToDateTime() Method
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
            string[] values = {"01/02/09", "2009/02/03",
                "01/2009/03", "01/02/2009", "01/02/23"};

            // calling get() Method
            Console.WriteLine("Converted string value "+
                              "to specified DateTime: ");

            for (int j = 0; j < values.Length; j++) {

                get(values[j], cultures);
            }
            Console.WriteLine("\n\nvalue is not a properly "+
                          "formatted date and time string.");

            // converting string to specified bool
            DateTime val = Convert.ToDateTime("21/2009/03",
                                                 cultures);

            // display the converted string
            Console.Write(" {0}, ", val);
        }
        catch (FormatException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
    // Defining get() method
    public static void get(string s,
               CultureInfo cultures)
    {

        // converting string to specified bool
        DateTime val = Convert.ToDateTime(s, cultures);

        // display the converted string
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**
Converted string value to specified DateTime: 01/02/2009 00:00:00, 02/03/2009 00:00:00, 01/03/2009 00:00:00, 01/02/2009 00:00:00, 01/02/2023 00:00:00, value is not a properly formatted date and time string. Exception Thrown: System.FormatException

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.todatetime?view=netframework-4.7.2#System_Convert_ToDateTime_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.todatetime?view=netframework-4.7.2#System_Convert_ToDateTime_System_String_System_IFormatProvider_)