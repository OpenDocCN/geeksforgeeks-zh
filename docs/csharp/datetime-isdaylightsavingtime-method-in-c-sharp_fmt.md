# DateTime.IsDaylightSavingTime() 方法 (C#)

> 原文: [https://www.geeksforgeeks.org/datetime-isdaylightsavingtime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-isdaylightsavingtime-method-in-c-sharp/)

此方法用于指示该 `DateTime` 实例是否在当前时区的夏令时范围内。

## 语法

```csharp
public bool IsDaylightSavingTime();
```

## 返回值

如果 `Kind` 属性的值为 `Local` 或 `Unspecified`，并且该 `DateTime` 实例的值在本地时区的夏令时范围内，则该方法返回 `true`。如果 `Kind` 为 `Utc`，则返回 `false`。

## 示例

以下程序说明了 `DateTime.IsDaylightSavingTime()` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTime.IsDaylightSavingTime()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                1, 4, 0, 15);

// getting Typecode of date
        // using IsDaylightSavingTime() method;
        bool value = date.IsDaylightSavingTime();

// checking the condition
        if (value)
            Console.WriteLine("Instance of DateTime is within the"
                             + " daylight saving time range for"+
                                " the current time zone.");

else
            Console.WriteLine("Instance of DateTime is not within the"
                              + " daylight saving time range for the "+
                                    "current time zone.");
    }
}
```

**输出:**

> Instance of DateTime is not within the daylight saving time range for the current time zone.

### 示例 2

```cs
// C# program to demonstrate the
// DateTime.IsDaylightSavingTime()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// creating object of DateTime
        DateTime date = new DateTime(1970, 1,
                                 1, 4, 0, 15);

// getting Typecode of date
        // using IsDaylightSavingTime() method;
        bool value = date.IsDaylightSavingTime();

// checking the condition
        if (value)
            Console.WriteLine("Instance of DateTime is within the"
                              + " daylight saving time range for "+
                                "the current time zone.");

else
            Console.WriteLine("Instance of DateTime is not within the"
                              + " daylight saving time range for the "+
                                    "current time zone.");
    }
}
```

**输出:**

> Instance of DateTime is not within the daylight saving time range for the current time zone.

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.isdaylightsavingtime?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.isdaylightsavingtime?view=netframework-4.7.2)