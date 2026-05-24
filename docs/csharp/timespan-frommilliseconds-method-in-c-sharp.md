# 时间跨度。C# 中的 from 毫秒()方法

> 原文:[https://www . geeksforgeeks . org/timespan-from 毫秒-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-frommilliseconds-method-in-c-sharp/)

此方法用于获取表示指定毫秒数的时间跨度。

> **语法:**公共静态时间跨度从毫秒(双精度值)；
> 
> **参数:**
> **值**:该参数指定毫秒数。
> 
> **返回值**:返回一个新的表示值的 TimeSpan 对象。

**异常:**

*   **overowexception**:当给定的双精度值小于最小可能值或大于最大可能值，或者值为正数或负数时出现。
*   **参数异常:**如果值等于 NaN。

以下程序说明了**时间跨度的使用。从毫秒(双倍)**方法:

**程序 1:**

```cs
// C# program to demonstrate the
// TimeSpan.FromMilliseconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = 
               TimeSpan.FromMilliseconds(8233567398261.2);

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
The Timespan is : 95295.22:03:18.2610000

```

**程序 2:** 为*溢出异常*

```cs
// C# program to demonstrate the
// TimeSpan.FromMilliseconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            TimeSpan interval = 
              TimeSpan.FromMilliseconds(Double.NegativeInfinity);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . from 毫秒？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.frommilliseconds?view=netframework-4.7.2)