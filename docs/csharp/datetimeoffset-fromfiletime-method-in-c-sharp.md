# DateTimeOffset。C# 中的 FromFileTime()方法

> 原文:[https://www . geesforgeks . org/datetime offset-from file time-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-fromfiletime-method-in-c-sharp/)

**DateTimeOffset。FromFileTime(Int64)方法**用于将指定的 Windows 文件时间转换为等效的本地时间。

> **语法:**public static datetime offset from file time(长文件时间)；
> 这里，需要一个 Windows 文件时间，用刻度表示。
> 
> **返回值:**该方法返回一个表示文件时间的日期和时间的对象，偏移量设置为本地时间偏移量。
> 
> **异常:**如果文件时间小于零或文件时间大于*日期时间偏移量，该方法将给出**参数。最大值。刻度***。

以下程序说明了**日期时间偏移的使用。FromFileTime(Int64)** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.FromFileTime(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converts the specified Windows file time
            // to an equivalent local time.
            // instance using FromFileTime() method
            DateTimeOffset value = DateTimeOffset.FromFileTime(10000);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
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
DateTimeOffset is 01/01/1601 00:00:00 +00:00

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.FromFileTime(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converts the specified Windows file time
            // to an equivalent local time.
            // instance using FromFileTime() method
            DateTimeOffset value = DateTimeOffset.FromFileTime(-1);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . from file time？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromfiletime?view=netframework-4.7.2)