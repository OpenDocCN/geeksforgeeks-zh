# DateTimeOffset。C# 中的 ToUnixTimeSeconds()方法

> 原文:[https://www . geesforgeks . org/datetime offset-tounixtimeseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tounixtimeseconds-method-in-c-sharp/)

**DateTimeOffset。ToUnixTimeSeconds** 方法用于返回自 1970-01-01T00:00:00Z 以来经过的秒数。在返回 Unix 时间之前，此方法会将当前实例转换为世界协调时。此外，对于 1970-01-01T00:00:00Z 之前的日期和时间值，它将返回负值。

> **语法:**公共长 ToUnixTimeSeconds()；
> 
> **返回值:**此方法返回自 1970-01-01T00:00:00Z 以来经过的秒数。

以下程序说明了**日期时间偏移的使用。ToUnixTimeSeconds()** 方法:

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
        DateTimeOffset offset = new DateTimeOffset(2017,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Returns the number of seconds
        // that have elapsed since 1970-01-01T00:00:00Z.
        // instance using ToUnixTimeSeconds() method
        long value = offset.ToUnixTimeSeconds();

        // Display the time
        Console.WriteLine("Returns the number of"+
                         " seconds : {0}", value);
    }
}
```

**Output:**

```cs
Returns the number of seconds : 1496321700

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToUnixTimeSeconds()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of  DateTimeOffset
        DateTimeOffset offset = new DateTimeOffset(2017,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Returns the number of seconds
        // that have elapsed since 1970-01-01T00:00:00Z.
        // instance using ToUnixTimeSeconds() method
        long value = offset.ToUnixTimeSeconds();

        // Display the time
        Console.WriteLine("Returns the number of"+
                         " seconds : {0}", value);
    }
}
```

**Output:**

```cs
Returns the number of seconds : 1496321700

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . tounixtimeseconds？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tounixtimeseconds?view=netframework-4.7.2)