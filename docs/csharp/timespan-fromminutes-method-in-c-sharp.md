# 时间跨度。C# 中的 FromMinutes()方法

> 原文:[https://www . geesforgeks . org/timespan-from minutes-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromminutes-method-in-c-sharp/)

此方法用于获取表示指定分钟数的时间跨度，其中规格精确到最接近的毫秒。

> **语法:**公共静态时间跨度 FromMinutes(双精度值)；
> 
> **参数:**
> **值**:该参数指定分钟数，精确到最近的毫秒。
> 
> **返回值**:返回一个新的表示值的 TimeSpan 对象。

**异常:**

*   **overowexception:**如果给定的双精度值小于最小可能值或大于最大可能值，或者该值为正数或负数。
*   **ArgumentException:** 如果值为 NaN。

以下程序说明了**时间跨度的使用。从分钟(双倍)法**:

**例 1:**

```cs
// C# program to demonstrate the
// TimeSpan.FromMinutes(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = TimeSpan.FromMinutes(8.12345);
            Console.WriteLine("The Timespan is : {0}",
                                            interval);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
The Timespan is : 00:08:07.4070000

```

**例 2:** 为*溢出异常*

```cs
// C# program to demonstrate the
// TimeSpan.FromMinutes(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = 
               TimeSpan.FromMinutes(Double.PositiveInfinity);

            Console.WriteLine("The Timespan is : {0}",
                                            interval);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . from minutes？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromminutes?view=netframework-4.7.2)