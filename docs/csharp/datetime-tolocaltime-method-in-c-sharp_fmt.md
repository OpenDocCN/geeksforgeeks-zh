# DateTime.ToLocalTime() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-tolocaltime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tolocaltime-method-in-c-sharp/)

此方法用于将当前 `DateTime` 对象的值转换为本地时间。

> **语法：** `public DateTime ToLocalTime();`
>
> **返回值：** 此方法返回一个 `Kind` 属性为 `Local` 的对象，其值为与当前 `DateTime` 对象的值等效的本地时间。如果转换后的值太大而无法用 `DateTime` 对象表示，则返回 `MaxValue`；如果转换后的值太小而无法用 `DateTime` 对象表示，则返回 `MinValue`。

以下程序说明了 `DateTime.ToLocalTime()` 方法的使用。

**例 1：**

```cs
// C# program to demonstrate the
// DateTime.ToLocalTime()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2011, 1,
                                1, 4, 0, 15);

        // Converts the value of the current 
        // DateTime object to local time.
        // using ToLocalTime() method;
        DateTime value = date.ToLocalTime();

        // Display the TimeSpan
        Console.WriteLine("local time is {0}", value);
    }
}
```

**输出：**

```cs
local time is 01/01/2011 04:00:15
```

**例 2：**

```cs
// C# program to demonstrate the
// DateTime.ToLocalTime()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = DateTime.Now;

        // Converts the value of the current
        // DateTime object to local time.
        // using ToLocalTime() method;
        DateTime value = date.ToLocalTime();

        // Display the TimeSpan
        Console.WriteLine("local time is {0}", value);
    }
}
```

**输出：**

```cs
local time is 02/11/2019 05:13:37
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tolocaltime?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tolocaltime?view=netframework-4.7.2)