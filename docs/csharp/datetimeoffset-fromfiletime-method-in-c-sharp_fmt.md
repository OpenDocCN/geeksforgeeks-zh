# DateTimeOffset.FromFileTime() 方法

> 原文: [https://www.geeksforgeeks.org/datetimeoffset-fromfiletime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-fromfiletime-method-in-c-sharp/)

`DateTimeOffset.FromFileTime(Int64)` 方法用于将指定的 Windows 文件时间转换为等效的本地时间。

> **语法:**
> `public static DateTimeOffset FromFileTime(long fileTime);`
> 这里，需要一个 Windows 文件时间，用刻度表示。
>
> **返回值:**
> 该方法返回一个表示文件时间的日期和时间的对象，偏移量设置为本地时间偏移量。
>
> **异常:**
> 如果文件时间小于零或文件时间大于 `DateTimeOffset.MaxValue.Ticks`，该方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTimeOffset.FromFileTime(Int64)` 方法的使用:

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

**例 2:** 为 `ArgumentOutOfRangeException`

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

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromfiletime?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.fromfiletime?view=netframework-4.7.2)