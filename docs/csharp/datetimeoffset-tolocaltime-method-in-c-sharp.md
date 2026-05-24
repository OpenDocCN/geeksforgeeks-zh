# DateTimeOffset。C# 中的 ToLocalTime()方法

> 原文:[https://www . geeksforgeeks . org/datetimeoffset-to localtime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tolocaltime-method-in-c-sharp/)

**DateTimeOffset。ToLocalTime 方法**用于将当前的 DateTimeOffset 对象转换为表示本地时间的 DateTimeOffset 对象。

> **语法:**public dateoffset tolocaltime()；
> 
> **返回值:**此方法返回一个对象，该对象表示当前 DateTimeOffset 对象转换为本地时间的日期和时间。

以下程序说明了**日期时间偏移的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToLocalTime()
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

            // Converts the current DateTimeOffset object
            // to a DateTimeOffset object that represents 
            // the local time instance using the 
            // ToLocalTime() method
            DateTimeOffset value = offset.ToLocalTime();

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
DateTimeOffset is 06/01/2007 12:55:00 +00:00

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToLocalTime()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of  DateTimeOffset
        DateTimeOffset offset = new DateTimeOffset(2027,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Converts the current DateTimeOffset object
        // to a DateTimeOffset object that represents 
        // the local time instance using the 
        // ToLocalTime() method
        DateTimeOffset value = offset.ToLocalTime();

        // Display the time
        Console.WriteLine("DateTimeOffset is {0}", value);
    }
}
```

**Output:**

```cs
DateTimeOffset is 06/01/2027 12:55:00 +00:00

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dot net/API/system . datetimeoffset . tolocaltime？view = net framework-4 . 7 . 2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tolocaltime?view=netframework-4.7.2)