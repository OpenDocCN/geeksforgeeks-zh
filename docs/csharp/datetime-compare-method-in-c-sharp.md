# 日期时间。C# 中的 Compare()方法

> 原文:[https://www . geesforgeks . org/datetime-compare-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-compare-method-in-c-sharp/)

此方法用于比较 DateTime 的两个实例，并返回一个整数，该整数指示第一个实例是早于、等于还是晚于第二个实例。

**语法:**

```cs
public static int Compare (DateTime t1, DateTime t2);
```

**参数:**

*   **t1:** 第一个比较的对象。
*   **t2:** 要比较的第二个对象。

**返回值:**该方法返回一个有符号数，表示 T1 和 t2 的相对值。

> **小于零**:如果 T1 早于 t2。
> **零**:如果 t1 和 T2 一样。
> **大于零**:如果 t1 晚于 t2。

以下程序说明了*日期时间的使用。比较(日期时间，日期时间)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.Compare(DateTime,
// DateTime) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date1 = new DateTime(2010, 1, 
                                 1, 4, 0, 15);

        // creating object of DateTime
        DateTime date2 = new DateTime(2010, 1,
                                 1, 4, 0, 14);

        // comparing date1 and date2
        // using Compare() method;
        int value = DateTime.Compare(date1, date2);

        // checking
        if (value > 0)
            Console.Write("date1 is later than date2\. ");
        else if (value < 0)
            Console.Write("date1 is earlier than date2\. ");
        else
            Console.Write("date1 is the same as date2\. ");
    }
}
```

**Output:**

```cs
date1 is later than date2.

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.Compare(DateTime, 
// DateTime) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling check() method
        check(new DateTime(2010, 1, 3, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 4, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15),
              new DateTime(2010, 1, 5, 4, 0, 15));
    }

    public static void check(DateTime date1,
                            DateTime date2)
    {

        // comparing date1 and date2
        // using Compare() method;
        int value = DateTime.Compare(date1, date2);

        // checking
        if (value > 0)
            Console.WriteLine(" {0:d} is later than {1:d}. ",
                                               date1, date2);
        else if (value < 0)
            Console.WriteLine(" {0:d} is earlier than {1:d}. ",
                                                 date1, date2);
        else
            Console.WriteLine(" {0:d} is the same as {1:d}. ",
                                                date1, date2);
    }
}
```

**Output:**

```cs
01/03/2010 is earlier than 01/04/2010\. 
01/05/2010 is later than 01/04/2010\. 
01/05/2010 is the same as 01/05/2010.

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . compare？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.compare?view=netframework-4.7.2)