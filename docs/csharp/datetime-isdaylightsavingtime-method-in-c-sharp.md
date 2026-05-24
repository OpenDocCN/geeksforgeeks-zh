# 日期时间。C# 中的 IsDaylightSavingTime()方法

> 原文:[https://www . geesforgeks . org/datetime-is daylightsavingtime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-isdaylightsavingtime-method-in-c-sharp/)

此方法用于指示该日期时间实例是否在当前时区的夏令时范围内。

> **语法:**public bool is daylightsavingtime()；
> 
> **返回值:**如果“种类”属性的值为“本地”或“未指定”，并且该日期时间实例的值在本地时区的夏令时范围内，则该方法返回 *true* ，如果“种类”为 Utc，则返回 *false* 。

以下程序说明了**日期时间的使用。IsDaylightSavingTime()** 方法:

**例 1:**

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

**Output:**

> 日期时间的实例不在当前时区的夏令时范围内。

**例 2:**

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

**Output:**

> 日期时间的实例不在当前时区的夏令时范围内。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . is daylightsavingtime？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.isdaylightsavingtime?view=netframework-4.7.2)