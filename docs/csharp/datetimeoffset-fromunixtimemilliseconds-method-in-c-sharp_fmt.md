# DateTimeOffset.FromUnixTimeMilliseconds() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-fromunixtimemilliseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-fromunixtimemilliseconds-method-in-c-sharp/)

## 方法介绍

`DateTimeOffset.FromUnixTimeMilliseconds(Int64)` 方法用于将表示为自 1970-01-01T00:00:00Z 以来经过的毫秒数的 Unix 时间转换为 `DateTimeOffset` 值。

### 语法

```cs
public static DateTimeOffset FromUnixTimeMilliseconds(long milliseconds);
```

这里，它需要一个 Unix 时间，表示为自 1970-01-01T00:00:00Z（1970 年 1 月 1 日，世界协调时上午 12:00）以来经过的毫秒数。对于该日期之前的 Unix 时间，其值为负值。

### 返回值

这个方法返回一个日期和时间值，代表与 Unix 时间相同的时刻。

### 异常

如果毫秒数小于 -62,135,596,800,000 或毫秒数大于 253,402,300,799,999，此方法将给出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了 `DateTimeOffset.FromUnixTimeMilliseconds(Int64)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTimeOffset.FromUnixTimeMilliseconds(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Converts a Unix time expressed as 
            // the number of milliseconds that
            // have elapsed since 1970-01-01T00:00:00Z 
            // to a DateTimeOffset value.
            // instance using AddYears() method
            DateTimeOffset value = 
                DateTimeOffset.FromUnixTimeMilliseconds(100000);

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

**输出：**

```
DateTimeOffset is 01/01/1970 00:01:40 +00:00
```

### 示例 2：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTimeOffset.FromUnixTimeMilliseconds(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Converts a Unix time expressed as the
            // number of milliseconds that have elapsed 
            // since 1970-01-01T00:00:00Z to a DateTimeOffset
            // value instance using AddYears() method
            DateTimeOffset value = 
                  DateTimeOffset.FromUnixTimeMilliseconds(253502300799999);

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

**输出：**

```
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromunixtimemilliseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromunixtimemilliseconds?view=netframework-4.7.2)