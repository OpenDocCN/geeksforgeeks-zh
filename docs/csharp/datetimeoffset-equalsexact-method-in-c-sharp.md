# DateTimeOffset。C# 中的 EqualsExact()方法

> 原文:[https://www . geesforgeks . org/datetime offset-equalsexcact-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-equalsexact-method-in-c-sharp/)

**DateTimeOffset。equalsexcact(DateTimeOffset)方法**用于确定当前 DateTimeOffset 对象是否表示与指定的 datetime offset 对象相同的时间，是否具有相同的偏移量。

> **语法:**public bool equalsexcact(datetime offset other)；
> 这里，它将对象与当前的 DateTimeOffset 对象进行比较。
> 
> **返回值:**如果当前日期时间偏移对象和其他具有相同的日期时间值和相同的偏移值，则该方法返回*true*；否则，*假*。

以下程序说明了**日期时间偏移的使用。等式行为(日期时间偏移)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.EqualsExact(DateTimeOffset)
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
        // instance using EqualsExact() method
        bool value = offset1.EqualsExact(offset2);

        if (value) 
        {
            Console.Write("offset1 is same as offset2 ");
        }
        else 
        {
            Console.Write("offset1 is not same as offset2");
        }
    }
}
```

**Output:**

```cs
offset1 is not same as offset2

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.EqualsExact(DateTimeOffset)
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
        // instance using EqualsExact() method
        bool value = offset1.EqualsExact(offset2);

        if (value) 
        {
            Console.Write("offset1 is same as offset2 ");
        }
        else 
        {
            Console.Write("offset1 is not same as offset2");
        }
    }
}
```

**Output:**

```cs
offset1 is same as offset2

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime offset . equalsexcact？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.equalsexact?view=netframework-4.7.2)