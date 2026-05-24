# DateTimeOffset.ToUnixTimeMilliseconds() 方法

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-tounixtimemilliseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tounixtimemilliseconds-method-in-c-sharp/)

`DateTimeOffset.ToUnixTimeMilliseconds()` 方法用于返回自 `1970-01-01T00:00:00.000Z` 后经过的毫秒数。对于 `1970-01-01T00:00:00Z` 之前的日期和时间值，此方法将返回负值。

## 语法

```cs
public long ToUnixTimeMilliseconds()
```

## 返回值

该方法返回 `1970-01-01T00:00:00.000Z` 后经过的毫秒数。

以下程序说明了 `DateTimeOffset.ToUnixTimeMilliseconds()` 方法的使用。

### 示例 1

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
        // creating object of  DateTimeOffset
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

**输出：**

```cs
Returns the number of milliseconds : 1180702500000
```

### 示例 2

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
        // Creating object of  DateTimeOffset
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

**输出：**

```cs
Returns the number of milliseconds : -302439900000
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tounixtimemilliseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tounixtimemilliseconds?view=netframework-4.7.2)