# 用时间跨度法获取昨天日期的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-get-date-of-day-use-timespan-method/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-date-of-yesterday-using-timespan-method/)

TimeSpan 是一个用于表示时间间隔的结构，该时间间隔用于测量分钟、小时、天的正数和负数。仅当时间与某个特定日期无关时，它也用于表示一天中的时间。在本文中，我们将使用 TimeSpan 结构找到昨天的日期。

**语法:**

> TimeSpan 变量 _ name = new TimeSpan()；

我们可以使用以下方法获得特定日期的日、月和年:

*   **Date and time. Day:** is used to find the date represented by this instance.
*   **Date and time. Month:** used to find the month of the date represented by this instance.
*   **Date and time. Year:** used to find the year of the date represented by this instance.

**例:**

## c#

```cs
// C# program to find the date of 
// yesterday using TimeSpan Method
using System;

class GFG{

static void Main()
{

    // Subtract todays date with timespan
    // to find the yesterday date
    DateTime yesterday = DateTime.Now - new TimeSpan(1, 0, 0, 0);

    // Find the day, month and year of the yesterday's date
    Console.WriteLine("Yesterday Date: {0}/{1}/{2}",
                      yesterday.Day, yesterday.Month, 
                      yesterday.Year);
}
}
```

**输出:**

```cs
Yesterday Date: 28/11/2021
```

**说明:**在上面的例子中，首先我们用时间跨度为 1 减去今天的日期，找到昨天的日期。这里，我们使用日期时间获得今天的日期。现在方法。以日/月/YY 格式显示昨天的日期、月份和年份。