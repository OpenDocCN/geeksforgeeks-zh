# 日期时间。在 C# 中添加()方法

> 原文:[https://www . geesforgeks . org/datetime-add-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-add-method-in-c-sharp/)

此方法用于返回一个新的日期时间，该日期时间将指定时间跨度的值添加到此实例的值中。

**语法:**

```cs
public DateTime Add (TimeSpan value);
```

这里，*值*为正或负的时间间隔。

**返回值:**该方法返回一个对象，该对象的值是该实例表示的日期和时间与值表示的时间间隔之和。

**异常:**如果结果日期时间小于*最小值*或大于*最大值*，此方法将给出*argumentout of range exception*。

以下程序说明了*日期时间的使用。添加(时间跨度)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.Add(TimeSpan) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // creating object of DateTime
            DateTime date1 = new DateTime(2010, 1, 1,
                                           8, 0, 15);

            // creating object of TimeSpan
            TimeSpan duration = new TimeSpan(36, 0, 0, 0);

            // adding the TimeSpan of 36 days
            // using Add() method;
            DateTime date2 = date1.Add(duration);

            // Display the date1
            System.Console.WriteLine("DateTime before "+
                      "operation: {0:y} {0:dd}", date1);

            // Display the date2
            System.Console.WriteLine("\nDateTime after"+
                     " operation: {0:y} {0:dd}", date2);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime before operation: 2010 January 01

DateTime after operation: 2010 February 06

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.Add(TimeSpan) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime 
            // and initialize with MinValue
            DateTime date1 = DateTime.MinValue;

            // Display the date1
            Console.WriteLine("DateTime before "+
               "operation: {0:y} {0:dd}", date1);

            // creating object of TimeSpan
            TimeSpan duration = new TimeSpan(-36, 0, 0, 0);

            // adding the TimeSpan of 36 days
            // using Add() method;
            DateTime date2 = date1.Add(duration);

            // Display the date2
            Console.WriteLine("\nDateTime after"+
              " operation: {0:y} {0:dd}", date2);
        }

        catch (ArgumentOutOfRangeException e)
       {
            Console.WriteLine("\nThe resulting DateTime"+
                          " is less than the MinValue ");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime before operation: 0001 January 01

The resulting DateTime is less than the MinValue 
Exception Thrown: System.ArgumentOutOfRangeException

```

**注:**

*   Add 方法在执行日期运算时会考虑闰年和一个月中的天数。
*   此方法不更改此日期时间的值。相反，它返回一个新的日期时间，其值是此操作的结果。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.add?view=netframework-4.7.2)