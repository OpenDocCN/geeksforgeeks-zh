# DateTimeOffset.ToOffset() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-tooffset-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-tooffset-method-in-c-sharp/)

`DateTimeOffset.ToOffset(TimeSpan)` 方法用于将当前 `DateTimeOffset` 对象的值转换为偏移值指定的日期和时间。

> **语法：** `public DateTimeOffset ToOffset(TimeSpan offset);`
> 这里，`offset` 参数用于将 `DateTimeOffset` 值转换到的目标偏移量。
>
> **返回值：** 此方法返回一个对象，该对象等于原始的 `DateTimeOffset` 对象（也就是说，它们的 `ToUniversalTime()` 方法返回相同的时间点），但其 `Offset` 属性设置为 `offset`。
>
> **异常：**
>
> *   `ArgumentException`：如果结果 `DateTimeOffset` 对象的 `DateTime` 值早于 `DateTime.MinValue`，*或*结果 `DateTimeOffset` 对象的 `DateTime` 值晚于 `DateTime.MaxValue`。
> *   `ArgumentOutOfRangeException`：如果 `offset` 小于 -14 小时，或者 `offset` 大于 14 小时。

以下程序说明了 `DateTimeOffset.ToOffset()` 方法的使用：

## 例 1

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

// creating object of  DateTimeOffset
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

## 例 2：为 `ArgumentOutOfRangeException`

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

// creating object of  DateTimeOffset
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

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tooffset?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.tooffset?view=netframework-4.7.2)