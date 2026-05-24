# 日期时间。C# 中的 ToFileTime()方法

> 原文:[https://www . geesforgeks . org/datetime-tofiletime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tofiletime-method-in-c-sharp/)

此方法用于将当前日期时间对象的值转换为窗口文件时间。

> **语法:**public long to filetime()；
> 
> **返回值:**该方法返回当前 DateTime 对象的值，表示为 Windows 文件时间。
> 
> **异常:**如果生成的文件时间表示世界协调时 1601 年 1 月 1 日午夜 12:00 之前的日期和时间，此方法将给出*argumentout of range Exception*。

以下程序说明了**日期时间的使用。ToFileTime()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToFileTime()
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

            // converting current DateTime 
            // object to a Windows file time.
            // using ToFileTime() method;
            long value = date.ToFileTime();

            // Display the TimeSpan
            Console.WriteLine("Windows file time "+
                                  "is {0}", value);
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
Windows file time is 129383280150000000

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.ToFileTime()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(1600, 1,
                                    1, 4, 0, 15);

            // converting current DateTime
            // object to a Windows file time.
            // using ToFileTime() method;
            long value = date.ToFileTime();

            // Display the TimeSpan
            Console.WriteLine("Windows file time"+
                                " is {0}", value);
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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . tofiletime？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tofiletime?view=netframework-4.7.2)