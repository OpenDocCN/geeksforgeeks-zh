# DateTimeOffset.FromUnixTimeSeconds() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-fromunixtimeseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-fromunixtimeseconds-method-in-c-sharp/)

`DateTimeOffset.FromUnixTimeSeconds(Int64)` 方法用于将表示为自 1970-01-01T00:00:00Z 以来经过的秒数的 Unix 时间转换为 `DateTimeOffset` 值。

## 语法

```cs
public static DateTimeOffset FromUnixTimeSeconds(long seconds);
```

在这里，它需要一个 Unix 时间，表示为自 1970-01-01T00:00:00Z（1970 年 1 月 1 日，世界协调时上午 12:00）以来经过的秒数。对于该日期之前的 Unix 时间，其值为负值。

## 返回值

该方法返回代表与 Unix 时间相同时刻的日期和时间值。

## 异常

如果 `seconds` 小于 -62,135,596,800 或 `seconds` 大于 253,402,300,799，此方法将给出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了 `DateTimeOffset.FromUnixTimeSeconds(Int64)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTimeOffset.FromUnixTimeSeconds(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Converts a Unix time expressed
            // as the number of seconds
            // that have elapsed since 
            // 1970-01-01T00:00:00Z to a 
            // DateTimeOffset value instance 
            // using FromUnixTimeSeconds() method
            DateTimeOffset value = 
               DateTimeOffset.FromUnixTimeSeconds(10000);

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

```cs
DateTimeOffset is 01/01/1970 02:46:40 +00:00
```

### 例 2：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTimeOffset.FromUnixTimeSeconds(Int64)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Converts a Unix time expressed
            // as the number of seconds
            // that have elapsed since 
            // 1970-01-01T00:00:00Z to a 
            // DateTimeOffset value instance 
            // using FromUnixTimeSeconds() method
            DateTimeOffset value = 
              DateTimeOffset.FromUnixTimeSeconds(254402300799);

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

```cs
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromunixtimeseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromunixtimeseconds?view=netframework-4.7.2)