# 使用时间跨度方法获取明天日期的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-tomorrow-date-use-timespan-method/](https://www.geeksforgeeks.org/c-sharp-program-to-get-tomorrows-date-using-timespan-method/)

TimeSpan 是一个用于表示时间间隔的结构，该时间间隔用于测量分钟、小时、天的正数和负数。仅当时间与某个特定日期无关时，它也用于表示一天中的时间。在本文中，我们将使用 TimeSpan 结构找到明天的日期。

**语法:**

> TimeSpan 变量 _ name = new TimeSpan()；

我们可以使用以下方法获得特定日期的日、月和年:

*   **Date and time. Day:** is used to find the date represented by this instance.
*   **Date and time. Month:** used to find the month of the date represented by this instance.
*   **Date and time. Year:** used to find the year of the date represented by this instance.

**例:**

## c#

```cs
// C# program to find tomorrow's date
// Using TimeSpan Method
using System;

class GFG{

static void Main()
{

    // Add todays date with timespan of 1 to get
    // tomorrow date
    DateTime tomorrowDate = DateTime.Now + new TimeSpan(1, 0, 0, 0);

    // Displaying day, month and year of tomorrow's date
    Console.WriteLine("tomorrow Date: {0}/{1}/{2}",
                      tomorrowDate.Day, tomorrowDate.Month,
                      tomorrowDate.Year);
}
}
```

**输出:**

```cs
tomorrow Date: 30/11/2021
```

**说明:**在上面的例子中，首先我们通过将今天的日期加上时间跨度为 1 来找到明天的日期。这里，我们使用日期时间获得今天的日期。现在方法。以日/月/YY 格式显示明天的日期、月份和年份。