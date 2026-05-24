# 日期时间。C# 中的 DaysInMonth()方法

> 原文:[https://www . geesforgeks . org/datetime-days in month-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-daysinmonth-method-in-c-sharp/)

此方法返回指定月份和年份中的天数。此方法始终将月和年解释为公历的月和年，即使公历不是当前区域性的当前日历。

**语法:**

```cs
public static int DaysInMonth (int year, int month);
```

**返回值:**该方法返回指定年份的月份天数。例如，如果二月份的月份等于 2，返回值将是 28 或 29，这取决于该年是否是闰年。

**异常:**如果*月*小于 1 或大于 12 ***或*** *年*小于 1 或大于 9999，此方法将给出*argumentout of range 异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to demonstrate the
// DaysInMonth(Int32, Int32) Method
using System;

class GFG {

    // Main Method
    static void Main()
    {

        // taking month values
        int Dec = 12;
        int Feb = 2;

        // using the method
        int daysindec = DateTime.DaysInMonth(2008, Dec);

        Console.WriteLine(daysindec);

        // daysinfeb1 gets 29 because the
        // year 2016 was a leap year.
        int daysinfeb1 = DateTime.DaysInMonth(2016, Feb);

        Console.WriteLine(daysinfeb1);

        // daysinfeb2 gets 28 because
        // the year 2018 was not a leap year.
        int daysinfeb2 = DateTime.DaysInMonth(2018, Feb);

        Console.WriteLine(daysinfeb2);
    }
}
```

**输出:**

```cs
31
29
28

```

**例 2:**

```cs
// C# code to demonstrate the
// DaysInMonth(Int32, Int32) Method
using System;

class GFG {

    // Main Method
    static void Main()
    {

        // taking month and year's value
        int y = 10000;
        int m = 7;

        // using the method will give error
        // as the value of the year is greater
        // than 10000
        int res = DateTime.DaysInMonth(y, m);

        Console.WriteLine(res);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:年份必须介于 1 和 9999 之间。
> 参数名称:年

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . daysinmonth？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.daysinmonth?view=netframework-4.7.2)