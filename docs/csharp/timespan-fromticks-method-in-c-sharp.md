# 时间跨度。C# 中的 FromTicks()方法

> 原文:[https://www . geesforgeks . org/timespan-from picks-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromticks-method-in-c-sharp/)

此方法用于获取表示指定时间的时间跨度，其中规格以刻度为单位。

> **语法:**公共静态时间跨度 FromTicks(长值)；
> 
> **参数:**
> **值**:该参数指定代表一个时间的刻度数。
> 
> **返回值:**它返回一个新的 TimeSpan 对象，表示该值。

以下程序说明了**时间跨度的使用。从信号(Int64)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// TimeSpan.FromTicks() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        TimeSpan interval = TimeSpan.FromTicks(1234);
        Console.WriteLine("The Timespan is : {0}",
                                       interval);
    }
}
```

**Output:**

```cs
The Timespan is : 00:00:00.0001234

```

**例 2:**

```cs
// C# program to demonstrate the
// TimeSpan.FromTicks() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        TimeSpan interval = TimeSpan.FromTicks(999999);

        Console.WriteLine("The Timespan is : {0}",
                                        interval);
    }
}
```

**Output:**

```cs
The Timespan is : 00:00:00.0999999

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . from picks？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromticks?view=netframework-4.7.2)