# 如何使用 C# 中的内置函数获取一个月的总天数？

> 原文：`https://www.geeksforgeeks.org/how-to-get-a-total-number-of-days-in-a-month-using-built-in-functions-in-c-sharp/`

给定一年 `Y` 和月 `M`，任务是在 C# 中获取一个月的总天数。

**示例：**

```cs
Input: Y = 2020 N = 02
Output: 29

Input: Y = 1996 N = 06
Output: 30
```

## 方法一：使用 `DateTime.DaysInMonth(year, month)` 方法

该方法用于获取指定月份和年份的天数。

> **第一步：** 获取年份和月份。
>
> **第二步：** `DateTime.DaysInMonth()` 用于获取一个月的天数。
>
> ```cs
> int days = DateTime.DaysInMonth(year, month);
> ```
>
> **第三步：** 这个整数值是一个月中的天数。

下面是上述方法的实现：

### C#

```cs
// C# program to Get a Total Number
// of Days in a Month
using System;

public class GFG{

// function to get the full month name
    static int getdays(int year, int month)
    {
        int days = DateTime.DaysInMonth(year, month);

        return days;
    }

    static public void Main ()
    {
        int Y = 2020; // year
        int M = 02; // month

        Console.WriteLine("Total days in ("
            + Y + "/" + M + ") : "+ getdays(Y, M));
    }
}
```

**输出：**

```cs
Total days in (2020/2) : 29
```

## 方法二：使用 `CultureInfo.CurrentCulture.Calendar.GetDaysInMonth(year, month)` 方法

该方法用于获取指定月份和年份的天数。你需要使用 `System.Globalization` 命名空间。

> **第一步：** 获取年份和月份。
>
> **第二步：** `CultureInfo.CurrentCulture.Calendar.GetDaysInMonth()` 用于获取一个月中的天数。
>
> ```cs
> int days = CultureInfo.CurrentCulture.Calendar.GetDaysInMonth(year, month);
> ```
>
> **第三步：** 这个整数值是一个月中的天数。

下面是上述方法的实现：

### C#

```cs
// C# program to Get a Total Number
// of Days in a Month
using System;
using System.Globalization;

public class GFG{

// function to get the full month name
    static int getdays(int year, int month)
    {
        int days = CultureInfo.CurrentCulture.
            Calendar.GetDaysInMonth(year, month);

        return days;
    }

    static public void Main ()
    {
        int Y = 2020; // year
        int M = 02; // month

        Console.WriteLine("Total days in ("
            + Y + "/" + M + ") : "+ getdays(Y, M)
            + " days");
    }
}
```

**输出：**

```cs
Total days in (2020/2) : 29 days
```