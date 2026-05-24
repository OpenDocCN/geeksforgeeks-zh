# DateTimeOffset。C# 中的 ToUnixTimeMilliseconds()方法

> 原文:[https://www . geeksforgeeks . org/datetime offset-tounixtimemyers-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tounixtimemilliseconds-method-in-c-sharp/)

**DateTimeOffset。方法用于返回自 *1970-01-01T00:00:00.000Z* 后经过的毫秒数。对于 *1970-01-01T00:00:00Z* 之前的日期和时间值，此方法将返回负值。**

> **语法:**公共长 ToUnixTimeMilliseconds
> 
> **返回值:**该方法返回 *1970-01-01T00:00:00.000Z* 后经过的毫秒数。

以下程序说明了**日期时间偏移的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToUnixTimeMilliseconds()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of  DateTimeOffset
        DateTimeOffset offset = new DateTimeOffset(2007,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Returns the number of milliseconds
        // instance using ToUnixTimeMilliseconds() method
        long value = offset.ToUnixTimeMilliseconds();

        // Display the time
        Console.WriteLine("Returns the number of"+
                    " milliseconds : {0}", value);
    }
}
```

**Output:**

```cs
Returns the number of milliseconds : 1180702500000

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToUnixTimeMilliseconds()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Creating object of  DateTimeOffset
        DateTimeOffset offset = new DateTimeOffset(1960,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Returns the number of milliseconds
        // instance using ToUnixTimeMilliseconds() method
        long value = offset.ToUnixTimeMilliseconds();

        // Display the time
        Console.WriteLine("Returns the number "+
                "of milliseconds : {0}", value);
    }
}
```

**Output:**

```cs
Returns the number of milliseconds : -302439900000

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset .tounixtime 毫秒？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tounixtimemilliseconds?view=netframework-4.7.2)