# DateTimeOffset。C# 中的 AddTicks()方法

> 原文:[https://www . geeksforgeeks . org/datetimeoffset-addticks-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addticks-method-in-c-sharp/)

此方法用于返回一个新的 DateTimeOffset 对象，该对象向当前实例的值添加指定数量的刻度。

> **语法:**public datetime offset AddTicks(长刻度)；
> 这里，需要 100 纳秒的节拍数。该数字可以是负数或正数。
> 
> **返回值:**该方法返回一个对象，该对象的值是当前 DateTimeOffset 对象表示的日期和时间与刻度表示的刻度数之和。
> 
> **异常:**如果结果日期时间偏移值小于最小值或结果日期时间偏移值大于最大值，该方法将给出**argumentoutofrangerexception**。

以下程序说明了**日期时间偏移的使用。添加标记(Int64)** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.AddTicks(Int64)
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

            // adding a 100 nanoseconds of ticks
            // instance using AddTicks() method
            DateTimeOffset value = offset.AddTicks(10000000);

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
DateTimeOffset is 06/01/2007 07:55:01 -05:00

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.AddTicks(Int64)
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

            // adding a 100 nanoseconds of ticks
            // instance using AddTicks() method
            DateTimeOffset value = offset.AddTicks(10000000);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . addticks？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addticks?view=netframework-4.7.2)