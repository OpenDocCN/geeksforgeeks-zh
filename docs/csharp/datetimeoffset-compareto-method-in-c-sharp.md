# DateTimeOffset。C# 中的 CompareTo()方法

> 原文:[https://www . geeksforgeeks . org/datetimeoffset-compare to-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-compareto-method-in-c-sharp/)

**DateTimeOffset。CompareTo(DateTimeOffset)方法**用于将当前 DateTimeOffset 对象与指定的 DateTimeOffset 对象进行比较，并指示当前对象是早于、等于还是晚于第二个 DateTimeOffset 对象。

> **语法:**public int compare to(datetime offset other)；
> 这里，需要一个对象与当前的 DateTimeOffset 对象进行比较。
> 
> **返回值:**这个方法返回一个有符号整数，表示当前 DateTimeOffset 对象和其他对象之间的关系。
> 
> *   **小于零:**表示当前 DateTimeOffset 对象早于其他对象。
> *   **零:**表示当前 DateTimeOffset 对象与其他对象相同。
> *   **大于零:**表示当前 DateTimeOffset 对象晚于其他对象。

以下程序说明了**日期时间偏移的使用。比较(日期时间偏移)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.CompareTo(DateTimeOffset)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of  DateTimeOffset
        DateTimeOffset offset1 = new DateTimeOffset(2007,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // creating object of  DateTimeOffset
        DateTimeOffset offset2 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // comparing two offset1 and offset2
        // instance using CompareTo() method
        int value = offset1.CompareTo(offset2);

        if (value > 0) 
        {
            Console.Write("offset1 is later than offset2 ");
        }
        else if (value < 0) 
        {
            Console.Write("offset1 is earlier than offset2");
        }
        else 
        {
            Console.Write("offset1 is equal to offset2");
        }
    }
}
```

**Output:**

```cs
offset1 is later than offset2

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.CompareTo(DateTimeOffset)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of  DateTimeOffset
        DateTimeOffset offset1 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // creating object of  DateTimeOffset
        DateTimeOffset offset2 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // comparing two offset1 and offset2
        // instance using CompareTo() method
        int value = offset1.CompareTo(offset2);

        if (value > 0) 
        {
            Console.Write("offset1 is later than offset2 ");
        }
        else if (value < 0) 
        {
            Console.Write("offset1 is earlier than offset2");
        }
        else 
        {
            Console.Write("offset1 is equal to offset2");
        }
    }
}
```

**Output:**

```cs
offset1 is equal to offset2

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetimeoffset . compare to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.compareto?view=netframework-4.7.2)