# 日期时间。C# 中的 ToUniversalTime()方法

> 原文:[https://www . geesforgeks . org/datetime-to niversaltime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-touniversaltime-method-in-c-sharp/)

此方法用于将当前日期时间对象的值转换为协调世界时。

> **语法:**public datetime tounivasultima()；
> 
> **返回值:**此方法返回一个对象，其 Kind 属性为 UTC，其值为与当前 DateTime 对象的值相等的 Utc，如果转换后的值太大而无法用 DateTime 对象表示，则返回 *MaxValue* ，如果转换后的值太小而无法用 DateTime 对象表示，则返回 *MinValue* 。

以下程序说明了**日期时间的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToUniversalTime()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                1, 4, 0, 15);

        // getting UTC from DateTime
        // using ToUniversalTime() method;
        DateTime value = date.ToUniversalTime();

        // Display the ShortTime
        Console.WriteLine("UTC is {0}", value);
    }
}
```

**Output:**

```cs
UTC is 01/01/2010 04:00:15

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.ToUniversalTime()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling check() method
        check(new DateTime(2010, 1,
                     3, 4, 0, 15));

        check(new DateTime(2010, 1,
                     5, 4, 0, 15));
    }

    public static void check(DateTime date)
    {

        // getting UTC from DateTime
        // using ToUniversalTime() method;
        DateTime value = date.ToUniversalTime();

        // Display the ShortTime
        Console.WriteLine("UTC of {0} is {1}",
                                 date, value);
    }
}
```

**Output:**

```cs
UTC of 01/03/2010 04:00:15 is 01/03/2010 04:00:15
UTC of 01/05/2010 04:00:15 is 01/05/2010 04:00:15

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . to universal time？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.touniversaltime?view=netframework-4.7.2)