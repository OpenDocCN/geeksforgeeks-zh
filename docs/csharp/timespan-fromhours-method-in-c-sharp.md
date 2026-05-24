# 时间跨度。C# 中的 FromHours()方法

> 原文:[https://www . geesforgeks . org/timespan-from hours-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromhours-method-in-c-sharp/)

此方法用于获取表示指定小时数的时间跨度，精确到最接近的毫秒。

> **语法:**公共静态 TimeSpan FromHours(双精度值)；
> 
> **参数:**
> **值**:该参数指定小时数，精确到最近的毫秒。
> 
> **返回值**:返回一个新的表示值的 TimeSpan 对象。

**异常:**

*   **overowexception**:当给定的双精度值小于最小可能值或大于最大可能值，或者值为正数或负数时出现。
*   **参数异常:**如果值等于 NaN。

以下程序说明了**时间跨度的使用。从小时(双)法**:

**程序 1:**

```cs
// C# program to demonstrate the
// TimeSpan.FromDays(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = TimeSpan.FromHours(12.3459);
            Console.WriteLine("The Timespan is : {0}",
                                            interval);
        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
The Timespan is : 12:20:45.2400000

```

**程序 2:** 为*溢出异常*

```cs
// C# program to demonstrate the
// TimeSpan.FromDays(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = 
               TimeSpan.FromHours(Double.NegativeInfinity);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . from hours？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromhours?view=netframework-4.7.2)