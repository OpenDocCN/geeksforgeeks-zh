# DateTimeOffset。C# 中的 ToFileTime()方法

> 原文:[https://www . geesforgeks . org/datetime offset-tofiletime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tofiletime-method-in-c-sharp/)

**DateTimeOffset。ToFileTime 方法**用于将当前 DateTimeOffset 对象的值转换为 Windows 文件时间。

> **语法:**public long to filetime()；
> 
> **返回值:**该方法返回当前 DateTimeOffset 对象的值，表示为 Windows 文件时间。
> 
> **异常:**如果生成的文件时间表示公元 1601 年 1 月 1 日午夜之前的日期和时间，该方法将给出**argumentout of range Exception**。

以下程序说明了**日期时间偏移的使用。ToFileTime()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToFileTime()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of  DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007,
                    6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

            // Converts the value of the current
            // DateTimeOffset object to a Windows file time.
            // instance using ToFileTime() method
            long value = offset.ToFileTime();

            // Display the time
            Console.WriteLine("Windows file time is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Windows file time is 128251761000000000

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.ToFileTime()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of  DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(1600,
                    6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

            // Converts the value of the current
            // DateTimeOffset object to a Windows file time.
            // instance using ToFileTime() method
            long value = offset.ToFileTime();

            // Display the time
            Console.WriteLine("Windows file time is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . tofiletime？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tofiletime?view=netframework-4.7.2)