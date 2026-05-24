# DateTimeOffset.AddMilliseconds() 方法

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-addmilliseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addmilliseconds-method-in-c-sharp/)

此方法用于获取新的 `DateTimeOffset` 对象，该对象将指定的毫秒数添加到当前实例的值中。

## 语法

```cs
public DateTimeOffset AddMilliseconds(double milliseconds);
```

在这里，它需要整数和分数毫秒。该数字可以是负数或正数。

## 返回值

该方法返回一个对象，该对象的值是当前 `DateTimeOffset` 对象表示的日期和时间与 `milliseconds` 表示的整毫秒数之和。

## 异常

如果结果日期时间偏移值小于最小值或大于最大值，该方法将给出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了 `DateTimeOffset.AddMilliseconds(Double)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMilliseconds(Double)
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

            // a number of whole and fractional milliseconds
            // instance using AddMilliseconds() method
            DateTimeOffset value = offset.AddMilliseconds(2000);

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

**输出：**

```cs
DateTimeOffset is 06/01/2007 07:55:02 -05:00
```

### 例 2

为 `ArgumentOutOfRangeException` 示例：

```cs
// C# program to demonstrate the
// DateTimeOffset.AddMilliseconds(Double)
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

            // a number of whole and fractional milliseconds
            // instance using AddMilliseconds() method
            DateTimeOffset value = offset.AddMilliseconds(2000);

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

**输出：**

```cs
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addmilliseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addmilliseconds?view=netframework-4.7.2)