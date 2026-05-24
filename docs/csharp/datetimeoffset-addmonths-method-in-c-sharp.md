# DateTimeOffset。C# 中的 AddMonths()方法

> 原文:[https://www . geesforgeks . org/datetime offset-add months-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addmonths-method-in-c-sharp/)

此方法用于返回一个新的 DateTimeOffset 对象，该对象将指定月数添加到当前实例的值中。

> **语法:**public datetime offset add months(int months)；
> 在这里，需要几个月的时间。该数字可以是负数或正数。
> 
> **返回值:**该方法返回一个对象，该对象的值是当前 DateTimeOffset 对象表示的日期和时间与月份表示的月数之和。
> 
> **异常:**如果结果日期时间偏移值小于最小值或结果日期时间偏移值大于最大值，该方法将给出**argumentoutofrangerexception**。

以下程序说明了**日期时间偏移的使用。添加月份(Int32)** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMonths(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007,
                    6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

            // adding a specified number of whole and
            // fractional months to the value of this
            // instance using AddMonths() method
            DateTimeOffset value = offset.AddMonths(10);

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
DateTimeOffset is 04/01/2008 07:55:00 -05:00

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMonths(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTimeOffset
            DateTimeOffset offset = DateTimeOffset.MaxValue;

            // adding a specified number of whole and
            // fractional months to the value of this
            // instance using AddMonths() method
            DateTimeOffset value = offset.AddMonths(10);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . add months？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addmonths?view=netframework-4.7.2)