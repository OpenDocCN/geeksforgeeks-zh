# DateTimeOffset。C# 中的 ToOffset()方法

> 原文:[https://www . geeksforgeeks . org/datetimeoffset-tooffset-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tooffset-method-in-c-sharp/)

**DateTimeOffset。ToOffset(TimeSpan)方法**用于将当前 DateTimeOffset 对象的值转换为偏移值指定的日期和时间。

> **语法:**public datetime offset ToOffset(time span offset)；
> 这里，需要偏移量来将 DateTimeOffset 值转换为。
> 
> **返回值:**此方法返回一个对象，该对象等于原始的 DateTimeOffset 对象(也就是说，它们的 ToUniversalTime()方法返回相同的时间点)，但其 Offset 属性设置为 Offset。
> 
> **异常:**
> 
> *   **参数异常**如果结果日期时间偏移对象的日期时间值早于最小值。*或*结果日期时间偏移对象的日期时间值晚于*最大值*。
> *   **argumentoutofrangerexception**如果偏移量小于-14 小时。或者偏移量大于 14 小时。

以下程序说明了**日期时间偏移的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.ToOffset(TimeSpan)
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

            // Converts the value of 
            // the current DateTimeOffset
            // object to the date and time 
            // specified by an offset value.
            // instance using ToOffset() method
            DateTimeOffset value = offset.ToOffset(new TimeSpan(-5, 1, 0));

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTimeOffset is 06/01/2007 07:56:00 -04:59

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.ToOffset(TimeSpan)
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

            // Converts the value of the
            // current DateTimeOffset
            // object to the date and time 
            // specified by an offset value.
            // instance using ToOffset() method
            DateTimeOffset value = offset.ToOffset(new TimeSpan(5, 1, 0));

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentException e) 
        {
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . tooffset？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tooffset?view=netframework-4.7.2)