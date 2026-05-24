# 使用时间跨度方法获取明天日期的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-get-tomorrows-date-using-timespan-method/](https://www.geeksforgeeks.org/c-sharp-program-to-get-tomorrows-date-using-timespan-method/)

`TimeSpan` 是一个用于表示时间间隔的结构，该时间间隔用于测量分钟、小时、天的正数和负数。仅当时间与某个特定日期无关时，它也用于表示一天中的时间。在本文中，我们将使用 `TimeSpan` 结构找到明天的日期。

## 语法

> `TimeSpan` 变量名 = new `TimeSpan()`；

我们可以使用以下方法获得特定日期的日、月和年：

*   **`DateTime.Day`**：用于查找此实例表示的日期。
*   **`DateTime.Month`**：用于查找此实例表示的日期的月份。
*   **`DateTime.Year`**：用于查找此实例表示的日期的年份。

## 示例

### C# 代码

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

### 输出

```cs
tomorrow Date: 30/11/2021
```

### 说明

在上面的例子中，首先我们通过将今天的日期加上时间跨度为 1 来找到明天的日期。这里，我们使用 `DateTime.Now` 获得今天的日期。现在方法以日/月/YY 格式显示明天的日期、月份和年份。