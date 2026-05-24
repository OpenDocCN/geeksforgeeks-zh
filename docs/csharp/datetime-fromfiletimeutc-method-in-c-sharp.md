# 日期时间。C# 中的 FromFileTimeUtc()方法

> 原文:[https://www . geesforgeks . org/datetime-from filetimeutc-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-fromfiletimeutc-method-in-c-sharp/)

**日期时间。FromFileTimeUtc(Int64)方法**用于将指定的 Windows 文件时间转换为等效的 Utc 时间。

> **语法:**public static DateTime from fileTime utc(长文件时间)；
> 这里，需要一个 Windows 文件时间，用刻度表示。
> **返回值:**该方法返回一个对象，该对象表示文件时间参数表示的日期和时间的 UTC 时间等价物。
> **异常:**如果*文件时间*小于 0 或代表大于最大值的时间，此方法将给出**argumentout of range Exception**。

以下程序说明了**日期时间的使用。【方法:
**例 1:**** 

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// DateTime.FromFileTimeUtc(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting 2500000000000 file
            // time represented in ticks
            // into UTC Time format
            // using FromBinary() method
            DateTime date2 = DateTime.FromFileTimeUtc(2500000000000);

            // Display the date2
            System.Console.WriteLine("DateTime after"
                + " operation: {0:y} {0:dd}", date2);

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
DateTime after operation: 1601 January 03
```

**例 2:** 为*argumentout of rangeexception*为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// DateTime.FromFileTimeUtc(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting -1 file time
            // represented in ticks
            // into DateTime format
            // using FromFileTimeUtc() method
            DateTime date2 = DateTime.FromFileTimeUtc(-1);

            // Display the date2
            System.Console.WriteLine("\nDateTime after"
                  + " operation: {0:y} {0:dd}", date2);

        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("fileTime is less than 0 ");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:** 

```cs
fileTime is less than 0 
Exception Thrown: System.ArgumentOutOfRangeException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . from filetimeutc？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.fromfiletimeutc?view=netframework-4.7.2)