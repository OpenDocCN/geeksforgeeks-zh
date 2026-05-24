# DateTimeOffset。C# 中的 AddMinutes()方法

> 原文:[https://www . geesforgeks . org/datetime offset-add minutes-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addminutes-method-in-c-sharp/)

此方法用于获取一个新的 DateTimeOffset 对象，该对象将指定数量的整数和分数分钟添加到当前实例的值中。

> **语法:**public datetime offset AddMinutes(双分钟)；
> 这里，需要若干整分钟和分数分钟。该数字可以是负数或正数。
> 
> **返回值:**返回一个对象，其值为当前 DateTimeOffset 对象表示的日期和时间与分钟表示的分钟数之和。
> 
> **异常:**如果结果日期时间偏移值小于最小值或结果日期时间偏移值大于最大值，该方法将给出**参数**

以下程序说明了**日期时间偏移的使用。添加分钟(双倍)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMinutes(Double)
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
            // fractional minutes to the value of this
            // instance using AddMinutes() method
            DateTimeOffset value = offset.AddMinutes(10);

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
DateTimeOffset is 06/01/2007 08:05:00 -05:00

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMinutes(Double)
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
            // fractional minutes to the value of this
            // instance using AddMinutes() method
            DateTimeOffset value = offset.AddMinutes(10);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . add minutes？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addminutes?view=netframework-4.7.2)