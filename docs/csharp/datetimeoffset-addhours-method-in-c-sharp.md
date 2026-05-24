# DateTimeOffset。C# 中的 AddHours()方法

> 原文:[https://www . geesforgeks . org/datetime offset-add hours-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addhours-method-in-c-sharp/)

此方法用于返回一个新的 DateTimeOffset 对象，该对象将指定数量的整数和小数小时添加到此实例的值中。

> **语法:**public datetime offset AddHours(双小时)；
> 在这里，它需要几个整数和分数小时。
> 
> **返回值:**该方法返回一个对象，其值为当前 DateTimeOffset 对象表示的日期和时间与小时数表示的小时数之和。
> 
> **异常:**如果结果日期时间偏移值小于最小值或结果日期时间偏移值大于最大值，该方法将给出**argumentoutofrangerexception**。

以下程序说明了**日期时间偏移的使用。添加小时(双倍)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.AddHours(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of  DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007,
                    6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

            // adding a specified number of whole and 
            // fractional hours to the value of this 
            // instance using AddHours() method
            DateTimeOffset value = offset.AddHours(10);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTimeOffset is 06/01/2007 17:55:00 -05:00

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.AddHours(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of  DateTimeOffset
            DateTimeOffset offset = DateTimeOffset.MaxValue;

            // adding a specified number of whole and
            // fractional days to the value of this instance.
            // using AddHours(Double) method;
            DateTimeOffset value = offset.AddHours(10);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) {
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . addhours？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addhours?view=netframework-4.7.2)