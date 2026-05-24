# DateTime.Subtract() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-subtract-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-subtract-method-in-c-sharp/)

此方法用于从此实例中减去指定的时间或持续时间。此方法的重载列表中有 2 种方法，如下所示：

*   `Subtract(DateTime)`
*   `Subtract(TimeSpan)`

## DateTime.Subtract(DateTime)

此方法用于从此实例中减去指定的日期和时间。

> **语法：** `public TimeSpan Subtract(DateTime value);`
>
> **返回值：** 此方法返回的时间间隔等于此实例表示的日期和时间减去 `value` 表示的日期和时间。
>
> **异常：** 如果结果小于 `MinValue` 或大于 `MaxValue`，此方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTime.Subtract(DateTime)` 方法的使用：

### 例 1：

```cs
// C# program to demonstrate the
// DateTime.Subtract(DateTime)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of DateTime
            DateTime date1 = new DateTime(2011, 1,
                                     1, 4, 0, 15);

// creating object of DateTime
            DateTime date2 = new DateTime(2010, 1,
                                     1, 4, 0, 15);

// getting ShortTime from DateTime
            // using Subtract() method;
            TimeSpan value = date1.Subtract(date2);

// Display the TimeSpan
            Console.WriteLine("TimeSpan between date1"+
                           " and date2 is {0}", value);
        }

catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
TimeSpan between date1 and date2 is 365.00:00:00
```

### 例 2：

```cs
// C# program to demonstrate the
// DateTime.Subtract(DateTime)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of DateTime
            DateTime date1 = DateTime.MinValue;

// creating object of DateTime
            DateTime date2 = new DateTime(11119999, 1,
                                     1, 4, 0, 15);

// getting ShortTime from DateTime
            // using Subtract() method;
            TimeSpan value = date1.Subtract(date2);

// Display the TimeSpan
            Console.WriteLine("TimeSpan between date1 "+
                         "and date2 is {0}", value);
        }

catch (ArgumentOutOfRangeException e) 
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

## DateTime.Subtract(TimeSpan)

此方法用于从该实例中减去指定的持续时间。

> **语法：** `public DateTime Subtract(TimeSpan value);`
>
> **返回值：** 此方法返回一个对象，该对象等于此实例表示的日期和时间减去 `value` 表示的时间间隔。
>
> **异常：** 如果结果小于 `MinValue` 或大于 `MaxValue`，此方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTime.Subtract(TimeSpan)` 方法的使用：

### 例 1：

```cs
// C# program to demonstrate the
// DateTime.Subtract(TimeSpan)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of DateTime
            DateTime date = new DateTime(2011, 1,
                                    1, 4, 0, 15);

// creating object of TimeSpan
            TimeSpan ts = new TimeSpan(1, 12,
                                     15, 16);

// getting ShortTime from 
            // subtracting DateTime and TimeSpan
            // using Subtract() method;
            DateTime value = date.Subtract(ts);

// Display the TimeSpan
            Console.WriteLine("DateTime between date "+
                           "and ts is {0}", value);
        }

catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime between date and ts is 12/30/2010 15:44:59
```

### 例 2：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTime.Subtract(TimeSpan)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of DateTime
            DateTime date = DateTime.MinValue;

// creating object of TimeSpan
            TimeSpan ts = new TimeSpan(1, 12, 15, 16);

// getting ShortTime from subtracting 
            // DateTime and TimeSpan
            // using Subtract() method;
            DateTime value = date.Subtract(ts);

// Display the TimeSpan
            Console.WriteLine("DateTime between date"+
                         " and ts is {0}", value);
        }

catch (ArgumentOutOfRangeException e)
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

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.subtract?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.subtract?view=netframework-4.7.2)