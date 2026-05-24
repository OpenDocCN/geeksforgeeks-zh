# 时间跨度。C# 中的 Compare()方法

> 原文:[https://www . geesforgeks . org/timespan-compare-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-compare-method-in-c-sharp/)

此方法用于比较两个时间跨度值，并返回一个整数值，该整数值指示第一个值是短于、等于还是长于第二个值。

> **语法:**公共静态 int Compare (TimeSpan t1，time span T2)；
> 
> **参数:**
> **t1** :指定第一次比较的时间间隔。
> **t2** :指定将被比较的第二个时间间隔。
> 
> **返回值:**
> **-1** :如果 T1 比 T2 短。
> **0** :如果 t1 等于 t2。
> **1** :如果 T1 比 t2 长。

以下程序说明了**时间跨度的使用。比较(时间跨度，时间跨度)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// TimeSpan.Compare(TimeSpan, 
// TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating the TimeSpans
        TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
        TimeSpan t2 = new TimeSpan(1, 11, 15, 16);

        if (TimeSpan.Compare(t1, t2) == 1)
            Console.Write("t1 is greater than t2");

        else if (TimeSpan.Compare(t1, t2) == 0)
            Console.Write("t1 is equal to t2");

        else
            Console.Write("t2 is greater than t1");
    }
}
```

**Output:**

```cs
t1 is greater than t2

```

**例 2:**

```cs
// C# program to demonstrate the
// TimeSpan.Compare(TimeSpan, 
// TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating the TimeSpans
        TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
        TimeSpan t2 = new TimeSpan(4, 31, 15, 10);

        if (TimeSpan.Compare(t1, t2) == 1)
            Console.Write("t1 is greater than t2");

        else if (TimeSpan.Compare(t1, t2) == 0)
            Console.Write("t1 is equal to t2");

        else
            Console.Write("t2 is greater than t1");
    }
}
```

**Output:**

```cs
t2 is greater than t1

```

**例 3:**

```cs
// C# program to demonstrate the
// TimeSpan.Compare(TimeSpan, 
// TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating the TimeSpans
        TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
        TimeSpan t2 = new TimeSpan(3, 22, 35, 33);

        if (TimeSpan.Compare(t1, t2) == 1)
            Console.Write("t1 is greater than t2");

        else if (TimeSpan.Compare(t1, t2) == 0)
            Console.Write("t1 is equal to t2");

        else
            Console.Write("t2 is greater than t1");
    }
}
```

**Output:**

```cs
t1 is equal to t2

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . timespan . compare？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.compare?view=netframework-4.7.2)