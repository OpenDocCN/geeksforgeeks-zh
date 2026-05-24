# DateTimeOffset。C# 中的 Compare()方法

> 原文:[https://www . geesforgeks . org/datetime offset-compare-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-compare-method-in-c-sharp/)

**DateTimeOffset。比较(DateTimeOffset，DateTimeOffset)方法**用于比较两个 DateTimeOffset 对象，显示第一个是早于第二个，等于第二个，还是晚于第二个。

> **语法:**公共静态 int Compare (DateTimeOffset 第一，DateTimeOffset 第二)；
> 
> **参数:**
> **第一:**是第一个比较的对象。
> **第二:**是第二个比较的对象。
> 
> **返回值:**该方法返回一个有符号整数，表示第一个参数的值是早于、晚于还是等于第二个参数的值。
> 
> *   **小于零:**表示第一个早于第二个。
> *   **零:**表示第一等于第二。
> *   **大于零:**表示第一晚于第二。

以下程序说明了**日期时间偏移的使用。比较(日期时间偏移，日期时间偏移)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.Compare(DateTimeOffset, 
// DateTimeOffset) Method
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
        // instance using Compare() method
        int value = DateTimeOffset.Compare(offset1, offset2);

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

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTimeOffset.Compare(DateTimeOffset,
// DateTimeOffset) Method
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
        // instance using Compare() method
        int value = DateTimeOffset.Compare(offset1, offset2);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . compare？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.compare?view=netframework-4.7.2)