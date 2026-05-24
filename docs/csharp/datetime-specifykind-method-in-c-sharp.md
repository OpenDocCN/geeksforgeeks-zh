# 日期时间。在 C# 中指定 Kind()方法

> 原文:[https://www . geesforgeks . org/datetime-指定 c-sharp 中的 kind-method/](https://www.geeksforgeeks.org/datetime-specifykind-method-in-c-sharp/)

此方法用于创建一个新的日期时间对象，该对象具有与指定日期时间相同的刻度数，但被指定为本地时间、协调世界时(UTC)或两者都不是，如指定的*日期时间种类*值所示。

> **语法:**公共静态日期时间指定种类(日期时间值，日期时间种类)；
> 
> **参数:**
> **值:**正是日期和时间。
> **种类:**是枚举值之一，表示新对象是表示当地时间、世界协调时，还是两者都不表示。
> 
> **返回值:**该方法返回一个新对象，该对象的刻度数与 Value 参数表示的对象和 Kind 参数指定的 DateTimeKind 值相同。

以下程序说明了**日期时间的使用。指定种类(日期时间，日期时间种类)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.SpecifyKind(DateTime,
// DateTimeKind) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date = new DateTime(2005, 5,
                                6, 14, 34, 42);

        Console.WriteLine("Kind Before Using Method: "
                                          +date.Kind);

        // getting DateTime of same DateTime 
        // instance using SpecifyKind() method
        DateTime value = DateTime.SpecifyKind(date,
                            DateTimeKind.Local);

        Console.WriteLine("Kind After Using Method: " +
                                            value.Kind);

        Console.WriteLine("DateTime is {0}",
                                    value);
    }
}
```

**Output:**

```cs
Kind Before Using Method: Unspecified
Kind After Using Method: Local
DateTime is 05/06/2005 14:34:42

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.SpecifyKind(DateTime,
// DateTimeKind) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date = new DateTime(1970, 1,
                                1, 4, 0, 15);

        // getting DateTime of same DateTime 
        // instance using SpecifyKind() method
        DateTime value = DateTime.SpecifyKind(date,
                               DateTimeKind.Local);

        Console.WriteLine("DateTime is {0}", value);
    }
}
```

**Output:**

```cs
DateTime is 01/01/1970 04:00:15

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime .指定种类？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.specifykind?view=netframework-4.7.2)