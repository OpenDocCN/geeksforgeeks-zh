# DateTimeOffset.Add() 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-add-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-add-method-in-c-sharp/)

此方法用于返回一个新的 `DateTimeOffset` 对象，该对象将指定的时间间隔添加到此实例的值中。

## 语法

```cs
public DateTimeOffset Add(TimeSpan TimeSpan);
```

这里，它取一个 `TimeSpan` 对象，表示一个正的或负的时间间隔。

## 返回值

该方法返回一个对象，其值为当前 `DateTimeOffset` 对象表示的日期和时间与 `TimeSpan` 表示的时间间隔之和。

## 异常

如果结果日期时间偏移值小于最小值或结果日期时间偏移值大于最大值，此方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTimeOffset.Add(TimeSpan)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTimeOffset.Add(TimeSpan)
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

// creating object of TimeSpan
            TimeSpan elapsedTime = new TimeSpan(10, 0, 0);

// adding a specified time interval 
            // to the value of this instance.
            // using Add() method;
            DateTimeOffset value = offset.Add(elapsedTime);

// Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
DateTimeOffset is 06/01/2007 17:55:00 -05:00
```

### 示例 2：针对 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTimeOffset.Add(TimeSpan)
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

// creating object of TimeSpan
            TimeSpan elapsedTime = new TimeSpan(10, 0, 0);

// adding a specified time interval 
            // to the value of this instance.
            // using Add() method;
            DateTimeOffset value = offset.Add(elapsedTime);

// Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

catch (ArgumentOutOfRangeException e)
        {
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

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.add?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.add?view=netframework-4.7.2)