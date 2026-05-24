# DateTimeOffset 中的 AddDays() 方法 (C#)

> 原文: [https://www.geeksforgeeks.org/datetimeoffset-adddays-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-adddays-method-in-c-sharp/)

此方法用于返回一个新的 `DateTimeOffset` 对象，该对象将指定天数的整数和小数添加到此实例的值中。

## 语法

```cs
public DateTimeOffset AddDays(double days);
```

这里，`days` 参数需要若干个整数和小数的日子。

## 返回值

该方法返回一个对象，其值为当前 `DateTimeOffset` 对象表示的日期和时间与 `days` 参数表示的天数之和。

## 异常

如果结果日期时间偏移值小于 `DateTimeOffset.MinValue` 或结果日期时间偏移值大于 `DateTimeOffset.MaxValue`，该方法将给出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了 `DateTimeOffset.AddDays(Double)` 方法的使用。

### 例 1

```cs
// C# program to demonstrate the
// DateTimeOffset.AddDays(Double)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of  DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007, 6, 1, 7, 55, 0,
                                                     new TimeSpan(-5, 0, 0));

// adding a specified number of whole 
            // and fractional days to the value 
            // of this instance using AddDays(Double) 
            // method
            DateTimeOffset value = offset.AddDays(10);

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

**输出:**

```cs
DateTimeOffset is 06/11/2007 07:55:00 -05:00
```

### 例 2: 为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTimeOffset.AddDays(Double)
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

// adding a specified number of whole and
            // fractional days to the value of this instance.
            // using AddDays(Double) method;
            DateTimeOffset value = offset.AddDays(10);

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

**输出:**

```cs
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.adddays?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.adddays?view=netframework-4.7.2)