# 日期时间。C# 中的 ToString()方法| Set–1

> 原文:[https://www . geesforgeks . org/datetime-tostring-method-in-c-set-1/](https://www.geeksforgeeks.org/datetime-tostring-method-in-c-set-1/)

此方法用于将当前日期时间对象的值转换为其等效的字符串表示形式。该方法的重载列表中总共有 4 个方法:

*   **ToString(字串，档案格式提供者)**
*   **ToString(String)**
*   **ToString(档案格式提供者)**
*   **ToString()**

在这里，我们将只讨论前两种方法。

#### ToString(字符串文件格式提供程序)

此方法用于使用指定的格式和区域性特定的格式信息将当前日期时间对象的值转换为其等效的字符串表示形式。

> **语法:**公共字符串 ToString(字符串格式，IFormatProvider 提供程序)；
> 
> **参数:**
> **格式:**一个标准或自定义的日期和时间格式字符串。
> **提供程序:**提供区域性特定格式信息的对象。
> 
> **返回值:**此方法返回由格式和提供程序指定的当前 DateTime 对象的值的字符串表示形式。

**异常:**

*   **格式异常:**如果格式长度为 1，并且不是为*或*定义的格式说明符字符之一，则该格式不包含有效的自定义格式模式。
*   **ArgumentOutOfRangeException:**如果日期和时间超出提供程序使用的日历支持的日期范围。

以下程序说明了**日期时间的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToString(String, 
// IFormatProvider) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = 
                CultureInfo.CreateSpecificCulture("de-DE");

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F", "g", "G",
                                   "m", "o", "r","s", "t" };

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++) 
            {
                get(format[j], cultures);
            }
        }

        catch (FormatException e) 
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format,
                    CultureInfo cultures)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(2008, 10,
                                         1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format, cultures);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

```cs
Converts the value of the currentDateTime object to its equivalent string
 01.10.2008 
 Mittwoch, 1\. Oktober 2008 
 Mittwoch, 1\. Oktober 2008 17:04 
 Mittwoch, 1\. Oktober 2008 17:04:32 
 01.10.2008 17:04 
 01.10.2008 17:04:32 
 1\. Oktober 
 2008-10-01T17:04:32.0000000 
 Wed, 01 Oct 2008 17:04:32 GMT 
 2008-10-01T17:04:32 
 17:04

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// DateTime.ToString(String, 
// IFormatProvider) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = 
               CultureInfo.CreateSpecificCulture("de-DE");

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F", "g", "G",
                                                  "s", "x"};

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++) 
            {
                get(format[j], cultures);
            }
        }

        catch (FormatException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("format does not contain "+
                       "a valid custom format pattern.");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format,
                    CultureInfo cultures)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(2008, 
                                 10, 1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format, cultures);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

```cs
Converts the value of the currentDateTime object to its equivalent string
 01.10.2008 
 Mittwoch, 1\. Oktober 2008 
 Mittwoch, 1\. Oktober 2008 17:04 
 Mittwoch, 1\. Oktober 2008 17:04:32 
 01.10.2008 17:04 
 01.10.2008 17:04:32 
 2008-10-01T17:04:32 

format does not contain a valid custom format pattern.
Exception Thrown: System.FormatException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.ToString(String,
// IFormatProvider) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = 
              CultureInfo.CreateSpecificCulture("ar-SA");

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F",
                                   "g", "G","s" };

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++) {
                get(format[j], cultures);
            }
        }

        catch (FormatException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("format does not contain "+
                       "a valid custom format pattern.");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("The date and time is outside the range of dates"
                                  + "supported by the calendar used by ar-SA");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format,
                    CultureInfo cultures)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(2999,
                                 10, 1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format, cultures);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

```cs
Converts the value of the currentDateTime object to its equivalent string

The date and time is outside the range of datessupported by the calendar used by ar-SA
Exception Thrown: System.ArgumentOutOfRangeException

```

#### 字符串方法

此方法用于使用当前区域性的指定格式和格式约定，将当前日期时间对象的值转换为其等效的字符串表示形式。

> **语法:**公共字符串 ToString(字符串格式)；
> 这里它采用标准或自定义的日期和时间格式字符串。
> 
> **返回值:**这个方法返回一个字符串，表示当前日期时间对象的值，由格式指定。

**异常:**

*   **格式异常:**如果格式长度为 1，并且不是为 DateTimeFormatInfo 定义的格式说明符字符之一，或者*格式*不包含有效的自定义格式模式。
*   **argumentoutofrangerexception:**如果日期和时间在当前区域性使用的日历支持的日期范围之外。

下面的程序举例说明了**到字符串(String)** 方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToString(String) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F", "g",
                         "G", "m", "o", "r","s", "t" };

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++)
            {
                get(format[j]);
            }
        }

        catch (FormatException e)
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(2008,
                                 10, 1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

```cs
Converts the value of the currentDateTime object to its equivalent string
 10/01/2008 
 Wednesday, 01 October 2008 
 Wednesday, 01 October 2008 17:04 
 Wednesday, 01 October 2008 17:04:32 
 10/01/2008 17:04 
 10/01/2008 17:04:32 
 October 01 
 2008-10-01T17:04:32.0000000 
 Wed, 01 Oct 2008 17:04:32 GMT 
 2008-10-01T17:04:32 
 17:04

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// DateTime.ToString(String) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F",
                              "g", "G", "s", "x" };

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++)
            {
                get(format[j]);
            }
        }

        catch (FormatException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("format does not contain "+
                        "a valid custom format pattern.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(2008,
                                 10, 1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

```cs
Converts the value of the currentDateTime object to its equivalent string
 10/01/2008 
 Wednesday, 01 October 2008 
 Wednesday, 01 October 2008 17:04 
 Wednesday, 01 October 2008 17:04:32 
 10/01/2008 17:04 
 10/01/2008 17:04:32 
 2008-10-01T17:04:32 

format does not contain a valid custom format pattern.
Exception Thrown: System.FormatException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.ToString(String) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // declaring and intializing String array
            string[] format = {"d", "D", "f", "F", 
                                   "g", "G","s" };

            // calling get() Method
            Console.WriteLine("Converts the value of the current"
                   + "DateTime object to its equivalent string");

            for (int j = 0; j < format.Length; j++)
            {
                get(format[j]);
            }
        }

        catch (FormatException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("format does not contain "+
                       "a valid custom format pattern.");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\n");
            Console.WriteLine("The date and time are outside the range of dates "
                     + "supported by the calendar used by the current culture.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string format)
    {
        // Define date to be displayed.
        DateTime dateToDisplay = new DateTime(9999,
                                 13, 1, 17, 4, 32);

        // converting DateTime to specified string
        string val = dateToDisplay.ToString(format);

        // display the converted ulong value
        Console.WriteLine(" {0} ", val);
    }
}
```

**Output:**

> 将 currentDateTime 对象的值转换为其等效字符串
> 
> 日期和时间超出了当前区域性使用的日历支持的日期范围。
> 异常抛出:系统。argumentoutofrangerexception

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tostring?view=netframework-4.7.2)