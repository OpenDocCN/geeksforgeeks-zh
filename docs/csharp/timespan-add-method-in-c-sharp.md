# 时间跨度。在 C# 中添加()方法

> 原文:[https://www . geesforgeks . org/timespan-add-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-add-method-in-c-sharp/)

此方法用于获取新的 TimeSpan 对象，其值是指定的 TimeSpan 对象和此实例的总和。

> **语法**公共时间跨度添加(time span t)；
> 
> **参数:**
> **t** :该参数指定需要添加的时间间隔。
> 
> **返回值:**它返回一个新的时间跨度对象，其值是当前实例和 *t* 的值之和。

**异常** : **飞越异常**:当结果时间跨度小于最小可能值或大于最大可能值时发生。

以下程序说明了**时间跨度的使用。添加(时间跨度)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// TimeSpan.Add(TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating the TimeSpan object
            TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
            TimeSpan t2 = new TimeSpan(1, 11, 15, 16);
            TimeSpan variable = t1.Add(t2);

            Console.WriteLine("The Timespan is : {0}",
                                            variable);
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
The Timespan is : 5:09:50:49

```

**例 2:** 为*溢出异常*

```cs
// C# program to demonstrate the
// TimeSpan.Add(TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // the TimeSpan object
            TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
            TimeSpan t2 = TimeSpan.MaxValue;
            TimeSpan variable = t1.Add(t2);

            Console.WriteLine("The Timespan is : {0}",
                                            variable);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.add?view=netframework-4.7.2)