# 日期时间。C# 中的 AddYears()方法

> 原文:[https://www . geesforgeks . org/datetime-addyears-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addyears-method-in-c-sharp/)

此方法用于返回一个新的日期时间，该日期时间将指定的年数添加到此实例的值中。

**语法:**

```cs
public DateTime AddYears (int value);
```

这里*值*是年数。*值*参数可以是负数或正数。

**返回值:**该方法返回一个对象，该对象的值是该实例表示的日期和时间与*值*表示的年数之和。

**异常:**如果结果日期时间小于最小值或大于最大值，该方法将给出*argumentout of range Exception*。

以下程序说明了*日期时间的使用。AddYears(Int32)* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.AddYears(Int32) Method
using System;
using System.Globalization;

class GFG {

// Main Method
public static void Main()
{

    try {

        // creating object of DateTime
        DateTime date1 = new DateTime(2010, 1, 1,
                                        4, 0, 15);

        // adding the 8 Months
        // using AddYears() method;
        DateTime date2 = date1.AddYears(8);

        // Display the date1
        Console.WriteLine("DateTime before operation: "
                              + "{0:y} {0:dd}", date1);                             

        // Display the date2
        Console.WriteLine("\nDateTime after operation: "
                              + "{0:y} {0:dd}", date2);

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

DateTime after operation: 2018 January 01

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.AddYears(Int32) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime 
            // and initialize with MinValue
            DateTime date1 = DateTime.MaxValue;

            // Display the date1
            Console.WriteLine("DateTime before operation: "
                                  + "{0:y} {0:dd}", date1);

            // adding the TimeSpan of 8 Years
            // using AddYears() method;
            DateTime date2 = date1.AddYears(5);

            // Display the date2
            Console.WriteLine("DateTime before operation: "
                                  + "{0:y} {0:dd}", date2);

        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\nThe resulting DateTime is "+
                      "greater than the DateTime.MaxValue ");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime before operation: 9999 December 31

The resulting DateTime is greater than the DateTime.MaxValue 
Exception Thrown: System.ArgumentOutOfRangeException

```

**注:**

*   该方法不改变该 *DateTime* 对象的值。相反，它返回一个新的 DateTime 对象，其值是此操作的结果。
*   该方法计算结果年时考虑了闰年。结果日期时间对象的月份和时间部分与此实例保持相同。
*   如果当前实例表示闰年的闰日，返回值取决于目标日期:
    *   If 值+ DateTime。年份也是闰年，返回值代表当年的闰日。例如，如果 2016 年 2 月 29 日加上四年，则返回的日期为 2020 年 2 月 29 日。
    *   If 值+ DateTime。年份不是闰年，返回值代表当年闰日的前一天。例如，如果将一年加到 2016 年 2 月 29 日，则返回的日期是 2017 年 2 月 28 日。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . addyears？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addyears?view=netframework-4.7.2)